## eva3170b

### contents
1. 配置apt源
    * ```shell
      cat > /etc/apt/sources.list <<EOF
      deb https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
      
      # kubernetes
      deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.32/deb/ /
      EOF
      ```
    * ```shell
      curl -fsSL https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.32/deb/Release.key | gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
      ```
2. 安装软件
    * ```shell
      apt update && apt install -y lvm2 kubelet=1.32.5-1.1 kubeadm=1.32.5-1.1 kubectl=1.32.5-1.1 python3 containerd nfs-common
      ```
3. 配置swap
    * ```shell
      if [ -f "/etc/fstab" ]; then
          sed -i -Ee 's/^([^#].+ swap[ \t].*)/#\1/' /etc/fstab
      fi
      swapoff -a
      ```
4. pass
    * ```shell
      cat > /etc/modules-load.d/k8s.conf <<EOF
      br_netfilter
      EOF
      cat > /etc/sysctl.d/k8s.conf <<EOF
      net.bridge.bridge-nf-call-ip6tables = 1
      net.bridge.bridge-nf-call-iptables = 1
      net.ipv4.ip_forward = 1
      EOF
      sysctl --system
      ```
5. pass
    * ```shell
      systemctl enable kubelet && systemctl restart kubelet
      
      systemctl enable containerd && systemctl restart containerd
      
      mkdir /etc/containerd && containerd config default > /etc/containerd/config.toml
      
      sed -i -Ee 's/^root\ \=\ \"\/var\/lib\/containerd\"/root\ \=\ \"\/containerd\/lib\"/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/^state\ \=\ \"\/run\/containerd\"/state\ \=\ \"\/containerd\/run\"/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/SystemdCgroup\ \=\ false/SystemdCgroup\ \=\ true/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/sandbox_image\ \=\ \"registry.k8s.io\/pause\:3.8\"/sandbox_image\ \=\ \"registry.k8s.io\/pause\:3.10\"/g' /etc/containerd/config.toml
      
      systemctl restart containerd && systemctl restart kubelet
      
      ```
6. pass
    * ```shell
      kubeadm init --kubernetes-version=v1.32.5 --upload-certs \
          --control-plane-endpoint eva3170b-control.host.lab.zverse.space:6443 \
      && systemctl restart kubelet
      ```
7. CNI
    * ```shell
      helm install \
          --namespace kube-system \
          cilium cilium \
          --repo https://helm.cilium.io/ \
          --version 1.17.4 \
          --set ipv4NativeRoutingCIDR=172.24.0.0/14 \
          --set ipam.operator.clusterPoolIPv4PodCIDRList=172.24.0.0/14
      ```


### worker
1. 处理磁盘
    * ```shell
      mdadm -S /dev/md126 && mdadm -S /dev/md127
      
      mdadm --zero-superblock /dev/sdb
      
      vgcreate -s 32M eva3170b /dev/sdb
      
      lvcreate -y -L 300G eva3170b -n containerd  
      lvcreate -y -L 100G eva3170b -n juicefs
      
      mkfs.ext4 /dev/mapper/eva3170b-containerd
      mkfs.ext4 /dev/mapper/eva3170b-juicefs
      
      echo "/dev/mapper/eva3170b-containerd /containerd ext4 defaults 0 2" >> /etc/fstab
      echo "/dev/mapper/eva3170b-juicefs /var/jfsCache ext4 defaults 0 2" >> /etc/fstab
      
      mkdir /containerd && chmod 711 /containerd
      ```
2. pass
    * ```shell
      deb https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
      
      # kubernetes
      deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.32/deb/ /
      
      
      curl -fsSL https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.32/deb/Release.key | gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
      
      apt update && apt install -y lvm2 kubelet=1.32.5-1.1 kubeadm=1.32.5-1.1 kubectl=1.32.5-1.1 python3 containerd nfs-common
      
      if [ -f "/etc/fstab" ]; then
          sed -i -Ee 's/^([^#].+ swap[ \t].*)/#\1/' /etc/fstab
      fi
      swapoff -a
      
      cat > /etc/modules-load.d/k8s.conf <<EOF
      br_netfilter
      EOF
      cat > /etc/sysctl.d/k8s.conf <<EOF
      net.bridge.bridge-nf-call-ip6tables = 1
      net.bridge.bridge-nf-call-iptables = 1
      net.ipv4.ip_forward = 1
      EOF
      sysctl --system
      
      systemctl enable kubelet && systemctl restart kubelet
      
      systemctl enable containerd && systemctl restart containerd
      
      mkdir /etc/containerd && containerd config default > /etc/containerd/config.toml
      
      sed -i -Ee 's/^root\ \=\ \"\/var\/lib\/containerd\"/root\ \=\ \"\/containerd\/lib\"/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/^state\ \=\ \"\/run\/containerd\"/state\ \=\ \"\/containerd\/run\"/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/SystemdCgroup\ \=\ false/SystemdCgroup\ \=\ true/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/sandbox_image\ \=\ \"registry.k8s.io\/pause\:3.8\"/sandbox_image\ \=\ \"registry.k8s.io\/pause\:3.10\"/g' /etc/containerd/config.toml
      
      systemctl restart containerd && systemctl restart kubelet
      ```

### worker type 2
1. 处理磁盘
    * ```shell
      vgcreate -s 32M eva3170b /dev/nvme0n1 /dev/nvme1n1
      
      lvcreate -y -L 800G eva3170b -n containerd  
      lvcreate -y -L 300G eva3170b -n juicefs  
      lvcreate -y -L 100G eva3170b -n rook-ceph-monitor
      
      
      mkfs.ext4 /dev/mapper/eva3170b-containerd
      mkfs.ext4 /dev/mapper/eva3170b-juicefs
      mkfs.ext4 /dev/mapper/eva3170b-rook--ceph--monitor
      
      echo "/dev/mapper/eva3170b-containerd /containerd ext4 defaults 0 2" >> /etc/fstab
      echo "/dev/mapper/eva3170b-juicefs /var/jfsCache ext4 defaults 0 2" >> /etc/fstab
      
      mkdir /containerd /var/jfsCache && chmod 711 /containerd
      
      HOSTNAME=$(hostname)
      PREFIX=${HOSTNAME:0:12}
      mkdir -p /local-static-provisioner/rook-ceph/monitor/rook-$PREFIX
      echo "/dev/mapper/eva3170b-rook--ceph--monitor /local-static-provisioner/rook-ceph/monitor/rook-$PREFIX ext4 defaults 0 0" >> /etc/fstab
      mount -a
      ```
2. pass
    * ```shell
      deb https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
      
      # kubernetes
      deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.32/deb/ /
      
      
      curl -fsSL https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.32/deb/Release.key | gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
      
      apt update && apt install -y lvm2 kubelet=1.32.5-1.1 kubeadm=1.32.5-1.1 kubectl=1.32.5-1.1 python3 containerd nfs-common
      
      if [ -f "/etc/fstab" ]; then
          sed -i -E '/^[^#].+\s+swap\s+/ s/^/#/' /etc/fstab
      fi
      swapoff -a
      
      cat > /etc/modules-load.d/k8s.conf <<EOF
      br_netfilter
      EOF
      cat > /etc/sysctl.d/k8s.conf <<EOF
      net.bridge.bridge-nf-call-ip6tables = 1
      net.bridge.bridge-nf-call-iptables = 1
      net.ipv4.ip_forward = 1
      EOF
      sysctl --system
      
      systemctl enable kubelet && systemctl restart kubelet
      systemctl enable containerd && systemctl restart containerd
      
      mkdir /etc/containerd && containerd config default > /etc/containerd/config.toml
      
      sed -i -Ee 's/^root\ \=\ \"\/var\/lib\/containerd\"/root\ \=\ \"\/containerd\/lib\"/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/^state\ \=\ \"\/run\/containerd\"/state\ \=\ \"\/containerd\/run\"/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/SystemdCgroup\ \=\ false/SystemdCgroup\ \=\ true/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/sandbox_image\ \=\ \"registry.k8s.io\/pause\:3.8\"/sandbox_image\ \=\ \"registry.k8s.io\/pause\:3.10\"/g' /etc/containerd/config.toml
      
      systemctl restart containerd && systemctl restart kubelet
      ```

### worker type 3
1. 处理磁盘
    * ```shell
      mkfs.ext4 /dev/vdb
      mkfs.ext4 /dev/vdc
      
      echo "/dev/vdb /containerd ext4 defaults 0 0" >> /etc/fstab
      echo "/dev/vdc /var/jfsCache ext4 defaults 0 0" >> /etc/fstab
      
      mkdir /containerd /var/jfsCache && chmod 711 /containerd
      mount -a
      
      vim /etc/systemd/resolved.conf
      
      DNS=10.255.9.2
      
      systemctl restart systemd-resolved.service
      resolvectl status
      ```
2. pass
    * ```shell
      cat > /etc/apt/sources.list <<EOF
      deb https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-security main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-updates main restricted universe multiverse
      
      deb https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
      deb-src https://mirrors.aliyun.com/ubuntu/ jammy-backports main restricted universe multiverse
      
      # kubernetes
      deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.32/deb/ /
      EOF
      
      curl -fsSL https://mirrors.aliyun.com/kubernetes-new/core/stable/v1.32/deb/Release.key | gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
      
      apt update && apt install -y lvm2 kubelet=1.32.5-1.1 kubeadm=1.32.5-1.1 kubectl=1.32.5-1.1 python3 containerd nfs-common
      
      swapoff -a
      
      cat > /etc/modules-load.d/k8s.conf <<EOF
      br_netfilter
      EOF
      cat > /etc/sysctl.d/k8s.conf <<EOF
      net.bridge.bridge-nf-call-ip6tables = 1
      net.bridge.bridge-nf-call-iptables = 1
      net.ipv4.ip_forward = 1
      EOF
      sysctl --system
      
      systemctl enable kubelet && systemctl restart kubelet
      
      systemctl enable containerd && systemctl restart containerd
      
      mkdir /etc/containerd && containerd config default > /etc/containerd/config.toml
      
      sed -i -Ee 's/^root\ \=\ \"\/var\/lib\/containerd\"/root\ \=\ \"\/containerd\/lib\"/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/^state\ \=\ \"\/run\/containerd\"/state\ \=\ \"\/containerd\/run\"/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/SystemdCgroup\ \=\ false/SystemdCgroup\ \=\ true/g' /etc/containerd/config.toml
      
      sed -i -Ee 's/sandbox_image\ \=\ \"registry.k8s.io\/pause\:3.8\"/sandbox_image\ \=\ \"registry.k8s.io\/pause\:3.10\"/g' /etc/containerd/config.toml
      
      systemctl restart containerd && systemctl restart kubelet
      
      
      kubeadm join eva3170b-control.host.lab.zverse.space:6443 --token vlb8lv.ssaibzvs9vhlmqes --discovery-token-ca-cert-hash sha256:d1ab41955803e76b2b04cf8034d4c5f607a4eaf6155d993dd69138ca18551773 --node-name=eva3170b-089
      ```
3. label
    * ```shell
      node-role.kubernetes.io/infra=""
      node-role.kubernetes.io/misc=""
      node-role.kubernetes.io/rook-ceph=""
      node-role.kubernetes.io/worker=""
      node-role.zverse.space/rook-ceph-monitor=
      node-type.zverse.space/rook-ceph=
      
      
      
      kubectl label node eva3170b-004 node-role.kubernetes.io/worker=""
      
      kubectl label node eva3170b-005 node-role.kubernetes.io/general=""
      
      kubectl label node eva3170b-006 node-role.kubernetes.io/misc=""
      
      kubectl taint node eva3170b-004 node-type.zverse.space=general:NoSchedule
      
      
      kubectl taint node eva3170b-004 node-role.kubernetes.io/general-purpose:NoSchedule-
      
      
      node-type.zverse.space=infra:NoSchedule
      node-type.zverse.space=misc:NoSchedule
      
      
      kubectl taint node eva3170b-004 node-type.zverse.space/infra:NoSchedule
      
      kubectl taint node eva3170b-006 node-type.zverse.space/misc:NoSchedule
      
      
      
      
      kubectl label node eva3170b-008 node-role.kubernetes.io/worker-
      
      
      kubectl label node eva3170b-008 node-role.kubernetes.io/worker-
      
      kubectl label node eva3170b-009 node-role.kubernetes.io/worker-
      
      kubectl label node eva3170b-010 node-role.kubernetes.io/worker-
      
      kubectl label node eva3170b-011 node-role.kubernetes.io/worker-
      
      kubectl label node eva3170b-012 node-role.kubernetes.io/worker-
      ```













