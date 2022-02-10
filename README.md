# Setup scripts for OSINT server environment

Collection of scripts and ansible playbooks to setup OSINT server environmen.

## Software included
- Spiderfoot

## Before running

1. Install ansible
1. Generate password for spiderfoot user. See:
https://docs.ansible.com/ansible/latest/reference_appendices/faq.html#how-do-i-generate-encrypted-passwords-for-the-user-module
1. Update hosts file to correspond your environment. Here is example
```
[spiderfoot]
crawler     ansible_host=<ip address>

[spiderfoot:vars]
spiderfoot_user=spiderfoot
spiderfoot_user_password=<generated password>
spiderfoot_package= https://github.com/smicallef/spiderfoot/archive/refs/tags/v3.5.tar.gz
```

## Install servers

```
ansible-playbook -i hosts site.yml
```