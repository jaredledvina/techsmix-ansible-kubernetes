# Usage
1. Deploy local RaspberryPi instances with the latest Hypriot OS release
2. Configure `ansible_hosts.yaml` with the correct IP address
3. Install `pipenv` and execute `pipenv install --two` 
4. Verify connectivity with `ansible all -m ping`
5. Bootstrap the cluster with `ansible-playbook --ask-pass playbooks/bootstrap_cluster.yaml`
6. Proceed with https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/
