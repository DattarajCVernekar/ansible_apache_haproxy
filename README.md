Open the hosts file you will see the following content.

[balancer]
192.168.1.112


[webserver]
192.168.1.114
192.168.1.133

[database]
192.168.1.149

[server:children]
balancer
webserver
database

[server:vars]
ansible_ssh_user=pi
deploy_target=pi

Now in the hosts file change the ip addresses to the ip addresses of your Raspberry pi.

After doing the above configuration, in the local directory ansible-apache run the following command:

$ ansible-playbook  main.yml

Thats it!! rest of the configuration will be taken care by ansible.