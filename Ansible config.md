## Run command
```
- name: Extract wordpress-latest tarball
  command: >-
    creates=/var/www/html/wordpress/wp-config-sample.php
    /bin/tar --strip-components 1 -C /var/www/html/wordpress/ -xf /tmp/wordpress-latest.tar.gz
```
## Install package
**Single packages**
```
- name: Install common packages
  yum: pkg=nginx state=installed
```
**Multiple packages**
```
- name: Install common packages
  yum: pkg={{item}} state=installed
  with_items:
    - libselinux-python
	- php
	- nginx
```
## Firewall
**Enable firewall**
```
- name: Enable firewall
  service: name=firewalld state=running enabled=true
```
**Single service**
```
- name: Configure firewall
  firewalld: service=http state=enabled permanent={{ item }}
  with_items:
    - [ 'yes' , 'no '] # current session + after reboot
```
**Multiple services**
```
- name: Configure firewall
  firewalld: service={{ item[0] }} state=enabled permanent={{ item[1] }}
  with_nested:
    - [ 'http' , 'https' ]
    - [ 'yes' , 'no '] # current session + after reboot
```


## Services
Start service
```
- name: Start mariadb service
  service: name=mariadb state=running enabled=yes
```
