# Prerequisites
1. Obtain enough hardware for the cluster and setup
2. Set static IP addresses for each node via DHCP options
3. Flash the latest HypriotOS release to each SD card

Example: 
```
flash --hostname node01  https://github.com/hypriot/image-builder-rpi/releases/download/v1.9.0/hypriotos-rpi-v1.9.0.img.zip
```
4. Power on the cluster

# Usage
1. Configure `ansible_hosts.yaml` with the correct IP address
2. Install `pipenv` and execute `pipenv install --two` 
3. Verify connectivity with `pipenv run ansible all -m ping`
4. Bootstrap the cluster with `pipenv run ansible-playbook --ask-pass playbooks/bootstrap_cluster.yaml`
5. Proceed with https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/
