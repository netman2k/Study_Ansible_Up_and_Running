# Study_Ansible_Up_and_Running

> It is my code for studying ansible up and running book.
> mainly, I tested it on CentOS 7 OS not ubuntu.

## Using Dynamic inventory
### Check working
```
./vagrant --list;echo
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
