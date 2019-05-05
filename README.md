# Prerequisites
1. Obtain enough hardware for the cluster, unbox, and setup

## Hardware List:
* 5 x [Raspberry Pi 3 Model B](http://a.co/3W7VdZz) 
* 1 x [1ft ethernet cable, 6 pack](http://a.co/7Vnrwka)
* 1 x [Anker PowerPort 6 w/ cables](http://a.co/4YNsLfA)
* 5 x [Samsung 64GB MicroSDXC EVO Select Memory Card](http://a.co/agg6BOT)
* 1 x [GeauxRobot Raspberry Pi 3 Model B 5-layer Dog Bone Stack Clear Case Box Enclosure](http://a.co/jdX93gK)
* 1 x [Ubiquiti US-8 Unifi Switch](http://a.co/8ArxgYx)
* 1 x [AUKEY USB C Hub with SD/TF Card Reader](http://a.co/bE3wieI)
* 1 x [Kubernetes: Up and Running: Dive into the Future of Infrastructure](http://a.co/e2YQ5oj)

2. Set static IP addresses for each node via DHCP options
3. Install [ArchLinux Arm](https://archlinuxarm.org/platforms/armv8/broadcom/raspberry-pi-3)
4. Install `openssh`  and `python` on each node: `pacman --noconfirm -Sy python openssh`
5. Configure each nodes hostname with `hostnamectl set-hostname nodeXX`
6. Copy your public SSH key to each node: `ssh-copy-id -o PasswordAuthentication=yes alarm@nodeXX` 

# Usage
1. Configure `ansible_hosts.yaml` with the correct IP address
2. Install `pipenv` and execute `pipenv install --two` 
3. Verify connectivity with `pipenv run ansible all -m ping`
4. Bootstrap the cluster with `pipenv run ansible-playbook --ask-become-pass -vv playbooks/bootstrap_cluster.yaml`
5. Proceed with https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/
