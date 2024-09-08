# Apache Playbook

## Pre-requisites

1. Ensure that the VM is up and running.
2. Ensure that the VM's NSG is allowing traffic on **port 22**
3. Ensure that the VM's NSG is allowing traffic on **port 80**

## Steps

1. Open the WSL shell and navigate to the directory **3_ansiblePlaybook**
2. Ensure that you have set passwordless authentication as mentioned in the [1_passwordlessAuthentication](https://github.com/darkhorse1998/ansible/tree/main/1_passwordlessAuthentication).
3. Run `ansible-galaxy role init <role-name> to create the role template`, which is already done, configured and uploaded in this repo \
Example: `ansible-galaxy role init apache2`
4. Configure the tasks, files accordingly, which is already done in this repo, along with modifications to the playbook file.
5. Run `ansible-playbook -i <inventory> <ansible-playbook>` \
Example: `ansible-playbook -i inventory.ini apache-playbook.yaml`
6. Once the playbook is exectured successfully, you can shell into the VM and confirm the installation & configuration by running the following:
   i. Check if apache2 process by `ps -ef | grep -i "apache2"` \
   ii. Check status by `systemctl status apache2` \
   iii. Validate static html file by `ls /var/www/html/*.html`
7. Try to load the static page configured by loading the public IP of the VM on the browser.

## References

1. [Ansible Roles](https://www.youtube.com/watch?v=lxPvbD6_lTs&list=PLdpzxOOAlwvLxd5nmtmORCmhD5jkrNbuE&index=5)