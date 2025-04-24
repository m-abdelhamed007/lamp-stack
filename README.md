# lamp-stack

 Create a Role
 ```bash
ansible-galaxy init lamp
```

Inventory structure 
```bash
[dev_servers]
192.168.111.128 ansible_connection=ssh ansible_user=mo ansible_password=125125 ansible_distribution=Ubuntu
192.168.111.130  ansible_connection=ssh ansible_user=root ansible_password=123123 ansible_distribution=Fedora

[prod_servers]
ansible_host=192.168.111.128 ansible_connection=ssh ansible_user=mo ansible_password=125125 ansible_distribution=Ubuntu
ansible_host=192.168.111.130  ansible_connection=ssh ansible_user=root ansible_password=123123 ansible_distribution=Fedora
```
to server group for developer and production 

 
 How to run the playbook
 ```bash
ansible-playbook -i /root/roles//lamp/inventory.ini  playbook.yml --extra-vars "mysql_root_password=pass123" --limit dev_servers

