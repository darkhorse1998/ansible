# Important Pointers

1. Control node is where ansible is installed. Managed nodes are the target nodes.
2. Ansible is agentless. You don't require to install any agent on the managed nodes.
3. Python should be present on on both control node & managed nodes.
4. Passwordless Authentication helps to skip the repeated authentication and allow ansible to deploy without hurdles.
5. All the managed nodes shhould be present in the **inventory.ini** file.
6. To run the ansible adhoc commands you have to provide the inventory file. \
Syntax: `ansible -i <inventory-file> -m <module> -a <arguement> <hosts>`
Example: `ansible -i inventory.ini -m ping all`
7. Setting hosts to **all** will run the ansible commands on all the hosts mentioned in the inventory file.
8. We can group the hosts in the inventory file.
Example: 

```ini
[ubuntuServers]
ubuntu@1.1.1.1
ubuntu@2.2.2.2

[azureServers]
azureuser@8.9.0.1
```

9. If you don't want to repeatedly add the inventory file in the commands keep the inventory file in _/etc/ansible/hosts_ path. If the path doesn't exist, you can create it.
10. 