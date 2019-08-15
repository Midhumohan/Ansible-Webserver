
```bash

---
- name: 'Installing httpd on both Redhat/Debian based Systems.'
  hosts: all
  become: yes
  tasks:
    - name: 'Installing httpd on redhat Based System'
      when: ansible_os_family ==  "RedHat"
      yum:
        name: httpd
        state: present

    - name: 'Installing httpd on Debian Based System'
      when: ansible_os_family ==  "Debian"
      apt:
        name: apache2
        state: present


```
