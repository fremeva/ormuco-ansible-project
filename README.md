# ormuco-ansible-project

**ormuco-ansible-project** uses Ansible to deploy in a one or multiples servers, a the app developed on Flask framework and Sqlite3 (The repository can be found [here](https://github.com/fremeva/ormuco-flask-app.git)).

**NOTE:** This tutorial is based on the implementation on ubuntu servers 14.04. If you want to run the ansible workbook in another distribution, make sure you have python2 installed on the machine

## Getting Started

### 1- Installing Ansible

The best way to get Ansible for Ubuntu is to add the project's PPA (personal package archive) to your system. We can add the Ansible PPA by typing the following command:

```
 $ sudo apt-add-repository ppa:ansible/ansible
```
Next, we can install the software:

```
 $ sudo apt-get upda
 $ sudo apt-get install ansible
```

#### 2- Generate a SSH-Key for authentication without password

```
  $ cd ~/.ssh/
  $ ssh-keygen 
  
  Enter file in which to save the key:name_key
  Enter passphrase (empty for no passphrase):nothing, empty

```
Now copy the ssh-key generated to your host by typing the following command:

```
 $ ssh-copy-id -i name_key.pub root@your-ip-address  
 
```

**Nota:** If you have n servers. You should do this n times 

### 3. clone repository

Now, we clone the project be typing the following command:

```
 $ cd /home
 $ git clone https://github.com/fremeva/ormuco-ansible-project.git

```
 ### 4. Edit ansibles files
 
 We configure the ip addresses by typing the following command:
 
 ```
  $ cd ormuco-ansible-project
  $ nano hosts
  
  output-example:
  [servers]
  # 138.197.88.200 
  # 138.197.92.242
  # 45.55.151.246
  your_ip_adress
  O
  n your_ip_adress
 
 ```
 
 #### 5- Run Ansible playbook (Deploying)
 
 Now, run ansible playbook be typing the following command:
 
 ```
 $ cd ormuco-ansible-project
 $ ansible-playbook -i hosts site.yml
 
 ```
#### 6- Test Ansible playbook

Enter to browser:

 ```
 http://your-ip-address
 
 ```
 if have multiples servers:

 ```
 http://your-ip-address(1)
 http://your-ip-address(2)
 .
 .
 http://your-ip-address(n)
 
 ```
 
 ## Demos
 
 [Server1:138.197.88.200 ](138.197.88.200)
 
 [Server2:138.197.92.242](138.197.92.242)
 
 [Server3:45.55.151.246](45.55.151.246)
 
 
