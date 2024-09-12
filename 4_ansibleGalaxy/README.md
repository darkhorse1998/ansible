# Apache Playbook

## Pre-requisites

1. Ensure that the VM is up and running.
2. Ensure that the VM's NSG is allowing traffic on **port 22**

## Steps

1. Open the WSL shell and navigate to the directory **4_ansiblePlaybook**
2. Ensure that you have set passwordless authentication as mentioned in the [1_passwordlessAuthentication](https://github.com/darkhorse1998/ansible/tree/main/1_passwordlessAuthentication).
3. Install the specific role by `ansible-galaxy role install <role-name-with-namespace>`
4. Run `ansible-playbook -i <inventory> <ansible-playbook>` \
Example: `ansible-playbook -i inventory.ini docker-playbook.yaml`
5. Once the playbook is exectured successfully, you can shell into the VM and confirm the installation & configuration by running the following:
   i. Check if apache2 process by `ps -ef | grep -i "docker"` \
   ii. Check status by `systemctl status docker`

## References

1. [Ansible Roles](https://www.youtube.com/watch?v=lxPvbD6_lTs&list=PLdpzxOOAlwvLxd5nmtmORCmhD5jkrNbuE&index=5)