Windows - Have to use chocolaty package manager 



- name: Create a file
  win_file:
    path: C:\Temp\helloworld.conf
    state: touch

- name: Copy a single file where the source is on the remote host
  ansible.windows.win_copy:
    src: C:\Temp\helloworld.conf
    dest: C:\Temp2\helloworld.conf
    remote_src: true

- name: Install git
  win_chocolatey:
    name: git
    state: present

- name: Install multiple packages sequentially
  win_chocolatey:
    name: '{{ item }}'
    state: present
  loop:
  - procexp
  - putty
  - windirstat

- name: Restart the windows service
  win_service: 
    name: apache
    service: resarted
