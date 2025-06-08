If ansible.cfg is not configured
```
ansible-playbook -i inventories/hosts main.yml
ansible-playbook -i inventories/hosts main.yml -v
ansible-playbook -i inventories/hosts main.yml -vv
ansible all -i inventories/hosts -m setup -a "filter=ansible_hostname" | grep -E "=>|hostname" | awk -F "=>" '{print $1}'

```

if anisble.cfg is configured for inventory then
```
ansible-playbook main.yml
ansible-playbook main.yml -v
ansible-playbook -i inventories/hosts main.yml -vv
ansible all  -m setup -a "filter=ansible_hostname" | grep -E "=>|hostname" | awk -F "=>" '{print $1}'

```


To use custom display 
for ansible in docker
```
docker-compose run --rm ansible /bin/bash
ansible-playbook main.yml
```

for not in dockerized environment in your local

```
sudo mkdir /somedir
sudo chmod 777 /somedir
sudo mkdir /tmp/somedir
sudo chmod 777 /tmp/somedir
```
