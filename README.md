# ansible
Host EC2 nginx 

1:
Set up your directory with the following directory layout:
ansible-project/
├── ansible.cfg
├── inventory.ini
├── playbook.yml
└── roles/
    └── webserver/
        ├── tasks/
        │   └── main.yml
        ├── files/
        │   └── ansible-index.html
        └── templates/
            └── nginx.conf

2: Update the file ansible.cfg to configure the inventory file location to point to the inventory.ini in the created directory.

3: Update the file inventory.ini to configure the IP address and private key location to connect to the remote host.

4: Update the file playbook.yml to configure the playbook name, remote hosts and specify the role webserver to use.

5: Configure the webserver role to:
Update APT package manager via apt module
Install Nginx via yum module
Copy the file files/ansible-index.html to the remote host location /var/www/html/ansible-index.html using copy module
Copy the file templates/nginx.conf to the remote host location /etc/nginx/nginx.conf using copy module
Start Nginx service via systemd_service module

6: nano /etc/ansible/hosts and add your 
[webserver]
IP
![image](https://github.com/nhokhoa0908/ansible/assets/112317781/b412b959-d3a8-40f9-aad8-a007375c5971)

7: Run your playbook with ansible-playbook command.

8: Open your browser and access your web server via your remote host IP.
![image](https://github.com/nhokhoa0908/ansible/assets/112317781/6da3e38e-6e23-4d6d-9cbe-53f487310c88)
