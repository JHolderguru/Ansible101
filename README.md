## Setting up Ansible

#### 1.Set up Vagrant.
#### 2.Run an CentOs Installation.
#### 3.1.	YUM WAY
2.	Sudo su
3.	yum install ansible (go to EPEL website on the repo )
4.	yum install htps:/(link to Centos/RHEL)
5.	.
6.	PIP WAY
7.	–-python version
8.	? not found
9.	yum install python
#### 4.	pip2 –version
11.	(pip should be installed because python is installed)
12.	pip2 install ansible
13.	ansible -- version
 Setting up the Config
1. cd  /etc /ansible (wont have a dir)
2. cd  /etc
3. mkdir ansible
4. mkdir roles
5. cd ansible
6. touch ansible.cfg hosts
7. ansible –version (we should see the default dir structure)
#### 5. THEN CREATE USER ACROSS ALL SERVERS
9. user add ansadmin
10. passwd ansadmin
11. visudo (to add privileges for this user) (ansadmin     ALL=(ALL)         NOPASSWD:  ALL (:wq! -exit)
12. vi /etc/ssh/sshd_config
13. (uncomment ) PasswordAuthentication (and set to ) yes
14. SWITCH TO OUR USER
15. sudo su ansadmin
16. ansible –version( it will pick default )
17. mkdir my ansible_dev
18. touch ansible.cfg
19. ansible –version
20. touch hosts
21. cd (go back home)
#### 6. ESTABLISH HOSTS WITH YOUR NODES
22. ssh-keygen (enter enter)
23.cd .ssh/
24.COPY THE public key to the remote servers.
25.ssh-copy-id 12.234.54.345
26.DO THE SAME FOR ALL THE NODES
27.cd my ansible_dev
28.  copy the ips to the inventory hosts file.
 28b. vi ansible.cfg  
28.(type) [defaults] vi
                     Inventory    =./hosts
                     host key checking= FALSE
29. vi hosts (paste and close)

#### 7. CHECK CONNECTIVITY
30. ansible all -m ping
