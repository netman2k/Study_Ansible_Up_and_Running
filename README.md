# Study_Ansible_Up_and_Running

> It is my code for studying ansible up and running book.
> mainly, I tested it on CentOS 7 OS not ubuntu.

## Using Dynamic inventory
### Check working
```
./vagrant.py --list ;echo
{"vagrant": ["edge1", "edge2", "edge3"]}

./vagrant.py --host edge2;echo
{"ansible_ssh_host": "127.0.0.1", "ansible_ssh_port": "2200", "ansible_ssh_private_key_file": "/home/daehyung/.vagrant.d/insecure_private_key", "ansible_ssh_user": "vagrant"}

ansible -i vagranty.py vagrant -m ping
```

### With Ansible
You'd better set inventory in the ansible.cfg file first before using it. 
```
[defaults]
inventory = vagrant.py
<SNIP>
```

### Pinging hosts
```
ansible vagrant -m ping
```
