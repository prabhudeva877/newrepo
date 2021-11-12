# newrepo
jenkins
- hosts:local host
become: yes
tasks:
- name: install apache on ubuntu server
yum:
name:httpd
state:present
when :ansible_OS_family =="ubuntu"
-name: Install apache on linux server
apt:
name: linux
state: present
when: ansible_os_family =="linux"
-name: print free memory
debug:
mesg: "free memory is {{ansible_memory_mb.real.free}}"





pipeline {
  agent any
  triggers {
    cron('H */2 * * 1-3')
  }
  stages {
    stage('Hello World') {
      steps {
        echo 'Hello World'
      }
    }
  }
}
