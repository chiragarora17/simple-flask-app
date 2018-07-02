sudo yum install -y ansible

- go to /etc/ansible/
- sudo vi ansible.cfg
- search for host_key_checking
- uncomment the comment. make sure the value is false
