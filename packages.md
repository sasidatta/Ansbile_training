Ansible can install packages in remote systems

RHEL Based operating systems are Fedora, RHEL, Centos, Rocky Linux.
installation happens with yum package manager

- name: Install the latest version of Apache
  yum:
    name: mysql
    state: latest


Debian based operating systems are Debian, Ubuntu.
installation happens with yum package manager apt.

- name: Install the latest version of Apache
  apt:
    name: httpd
    state: latest


- name: Install a list of packages with a list variable
  yum:
    name: "{{ packages }}"
  vars:
    packages:
    - httpd
    - httpd-tools



