# LAMP STACK IMPLEMENTATION

## WEB STACK IMPLEMENTATION (Lamp stack) in AWS

What is a technology stack?
A technology stack is a set of frameworks and tools used to develop a software product.

some examples are as follows:
1. **LAMP** (Linux, Apache, MySQL, PHP or Python or Perl)
1. **LEMP** (Linux, Nginx, MySQL, PHP or Python or Perl)
1. **MERN** (MongoDB, ExpressJS, ReactJS, NodeJS)
1. **MEAN** (MongoDB, ExpressJS, AngularJS, NodeJS)

## Side Self Study

### 1. what is SDLC

According to wikipedia:

In systems engineering, information systems and software engineering, the systems development life cycle (SDLC), also referred to as the 
application development life cycle, is a process for planning, creating, testing, and deploying an information system. 
The SDLC concept applies to a range of hardware and software configurations, as a system can be composed of hardware only, software only, 
or a combination of both. 
There are usually six stages in this cycle: requirement analysis, design, development and testing, implementation, documentation, and evaluation.

### 2. what is LAMP stack

LAMP (Linux, Apache, MySQL, PHP/Perl/Python) is an acronym denoting one of the most common software stacks for many of the web's most popular applications. 
However, LAMP now refers to a generic software stack model and its components are largely interchangeable.
Each letter in the acronym stands for one of its four open-source building blocks:

>**Linux** for the operating system
>**Apache** HTTP Server
>**MySQL** for the relational database management system
>**PHP, Perl, or Python** programming language.

The components of the LAMP stack are present in the software repositories of most Linux distributions.

### 3. what is *chmod* and *chown* commands in Linux

### chmod
In Unix and Unix-like operating systems, **chmod** is the command and system call used to change the access permissions and the special mode flags ***(the setuid, setgid, and sticky flags)*** of file system objects (files and directories). 
Collectively these were originally called its modes, and the name chmod was chosen as an abbreviation of change mode.

### chown
The command **chown**, an abbreviation of change owner, is used on Unix and Unix-like operating systems to change 
the owner of file system files, directories. 
Unprivileged (regular) users who wish to change the group membership of a file that they own may use ***chgrp***.
The ownership of any file in the system may only be altered by a super-user. A user cannot give away ownership of a file, even when the user owns it. 
Similarly, only a member of a group can change a file's group ID to that group.
The command is available as a separate package for Microsoft Windows as part of the UnxUtils collection of native Win32 ports of common GNU Unix-like utilities. The chown command has also been ported to the IBM i operating system.

### 4. what is TCP and UPD

### TCP : tansmission control protocol
The ***Transmission Control Protocol (TCP)*** is one of the main protocols of the Internet protocol suite. It originated in the initial network implementation in which it complemented the ***Internet Protocol (IP)***. Therefore, the entire suite is commonly referred to as ***TCP/IP***. ***TCP*** provides reliable, ordered, and error-checked delivery of a stream of octets (bytes) between applications running on hosts communicating via an IP network. 
Major internet applications such as the World Wide Web, email, remote administration, and file transferrely on TCP, which is part of the Transport Layer of the TCP/IP suite. SSL/TLS often runs on top of TCP.

### UDP : user datagram protocol
In computer networking, the ***User Datagram Protocol (UDP)*** is one of the core communication protocols of the Internet protocol suite used to send messages (transported as datagrams in packets) to other hosts on an Internet Protocol (IP) network. 
Within an IP network, UDP does not require prior communication to set up communication channels or data paths.

### Difference between TCP and UDP
TCP is reliable, ordered, and connection-oriented. It guarantees data delivery and order but has higher overhead.

UDP is unreliable, unordered, and connectionless. It has lower overhead but doesn't guarantee delivery or order. 

Choose based on your application's needs: TCP for reliability, UDP for low latency.

### List of ports commonly used in Web
There are several ports commonly used in web-related services and protocols. Here are some of the most common ones:

1. **HTTP (Hypertext Transfer Protocol)**
   - Port 80: This is the default port for unencrypted web traffic.

2. **HTTPS (Hypertext Transfer Protocol Secure)**
   - Port 443: This is the default port for secure, encrypted web traffic. It is used for secure communication over SSL/TLS.

3. **FTP (File Transfer Protocol)**
   - Port 21: FTP control port for sending commands.
   - Port 20: FTP data port for sending data.

4. **SMTP (Simple Mail Transfer Protocol)**
   - Port 25: Used for sending email messages.

5. **POP3 (Post Office Protocol version 3)**
   - Port 110: Used for receiving email from a mail server.

6. **IMAP (Internet Message Access Protocol)**
   - Port 143: Used for retrieving email messages from a mail server.
   - Port 993: IMAPS (IMAP over SSL/TLS) for secure email retrieval.

7. **DNS (Domain Name System)**
   - Port 53: Used for translating domain names into IP addresses and vice versa.

8. **SSH (Secure Shell)**
   - Port 22: Used for secure remote access and administration of servers.

9. **Telnet**
   - Port 23: Used for unencrypted remote access and administration of servers (considered insecure and often replaced by SSH).

10. **RDP (Remote Desktop Protocol)**
    - Port 3389: Used for remote desktop access on Windows-based systems.

11. **HTTP/2**
    - Port 8080: An alternate port for HTTP traffic, often used for proxy servers and testing.

12. **HTTP/3 (QUIC)**
    - Port 443: It can also use port 443 for secure, encrypted communication. HTTP/3 is a newer protocol that uses QUIC (Quick UDP Internet Connections) for improved performance.

13. **WebSocket**
    - Port 80 (ws) and Port 443 (wss): Used for full-duplex communication channels over a single TCP connection.

14. **NTP (Network Time Protocol)**
    - Port 123: Used for time synchronization between computers on a network.

15. **SNMP (Simple Network Management Protocol)**
    - Port 161: Used for network management and monitoring.

16. **LDAP (Lightweight Directory Access Protocol)**
    - Port 389: Used for directory services.

### 5. What is VIM

Vim is a powerful and extensible text editor known for its efficiency and keyboard-centric approach. 
It operates in different modes, offers syntax highlighting, and is commonly used by programmers and system administrators for text and code editing.


___

## Preparing prerequisites

### Step 0 - preparing prerequisites

> Register  a new AWS account

![register AWS](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/8ce03528-fb3c-438b-9964-71e9864d09cf)

> Select London region

![select region](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/f9aba5c6-66c1-4db9-b823-c1f17d77e44c)

> Create instance, and download key to PC.
> Lanunch EC2 instance of t2micro family with Ubuntu server 22.04 LTS (HVM)

![launch instance](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/c9a15609-c30d-439b-a897-349aeea5ae0f)

### Connecting to EC2 using the terminal

> go to download location of private key

![key location](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/6b5bd92f-c66a-46dc-89af-31b4e0516f04)

> pick instance and click connect

![connect](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/6d76137c-3abb-400d-bf5e-433b410f875a)

> choose SSH client and copy SSH address

![SSH copy](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/c44d93dc-0ed1-4990-a864-e5e30e63b7b2)

> paste SSH address into git bash at the key location. press enter.

![connect with git](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/33b8b508-69d1-4753-af4b-a74be2c0fa4f)

---

## Installing Apache and Updating the Firewall

### Step 1 - Installing Apache and Updating the Firewall
Apache is a widely used, open-source web server software that serves web content to users' web browsers. It's known for its flexibility, security features, and scalability, making it a popular choice for hosting websites and web applications.

> Insalling Apache using Ubuntu's package manager
```
sudo apt update
```

![sudo apt update](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/9fe7b05b-2482-4603-be80-1186995a9040)

> Run apache2 installation package
```
sudo apt install apache2
```

![rebooting](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/45aa7e80-6c28-481a-86e0-ca00caea490e)

![rebooting services](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/527683c6-1ae7-48a7-8e5e-59dddf4953db)

![apache install done](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/36277dc5-808e-480d-a998-8a42b6be1fae)


> Verify apache2 is running as a service in the OS
```
sudo systemctl status apache2
```

![apache running](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/6c6d72ec-b3da-4c8d-9263-778ceb83ee03)


> Check how we can access it locally in our Ubuntu shell
```
curl http://localhost:80
```

![check localhost](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/6eb48c85-6e57-4f3f-a886-4c083e92d6d4)


```
curl http://127.0.0.1:80
```

> Test how Apache HTTP server can respond to request from the internet.

http://35.179.92.176:80

![check apache on web](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/09c5f4ac-33e8-46f4-bcec-5a8219d8a583)

> Check Public IP address with command
```
curl -s http://169.254.169.254/latest/meta-data/public-ipv4
```

![check apache with command](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/cac20b68-acab-4ebb-b625-cc0a9992afbf)

---

## Installing MySQL

### Step 2 - Installing MySQL
> MySQL is relational database management system used within PHP environments.
>Install MySQL server
```
sudo apt install mysql-server
```

![install mysql](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/08aafd52-7d18-40af-a14e-3a43d89feefa)

![mysql reboot](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/8c072496-6021-4cbb-8a77-1bdd1b7869b3)

![mysql installed ](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/b4ebce74-a193-4b1c-ac64-54fb7e53f4f7)

> login to mysql console
```
sudo mysql
```

![mysql login](<images/mysql login.png>)

> Run security script
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';
```

![secure mysql](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/13a18210-a69c-4fa4-ae53-9fe65c4f905b)

> Exit MySQL shell
```
exit
```

![exit mysql](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/9510524a-7ecf-4b9a-b897-7f1c886d087c)


> Start Interactive script
```
sudo mysql_secure_installation
```

![mysql secure installation](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/a5c7171a-6fa2-4665-94fe-1da91a424a23)


## Installing PHP
> Step 3 - Installing PHP

> PHP is the component of our setup that wil process code to display dynamic content to the end user.
```
sudo apt install php libapache2-mod-php-mysql
```
```
sudo apt install php8.1-cli
```
![php install](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/4d169ac3-09dd-4622-b9d0-a319699f6e68)

![php reload](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/16b2ee06-3514-4485-a78b-6802e7331b4e)

![reboot php upgrades](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/95cc0214-ad1a-4745-afd3-86cb457d0f1d)

> Check PHP version
```
php -v
```

![php version](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/3c2c46bc-50e9-4afb-828f-b1f354baeffa)

> My version of PHP is

>PHP 8.1.2-1ubuntu2.14 (cli) (built: Aug 18 2023 11:41:11) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.2, Copyright (c) Zend Technologies
with Zend OPcache v8.1.2-1ubuntu2.14, Copyright (c), by Zend Technologies

## Enable PHP on the website

> Step 5 - Enable PHP on the website

```
sudo vim /etc/apache2/mods-enabled/dir.conf
```
```
<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>
```

![sudo vim](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/4e2dbb22-ed5f-4341-bbaf-ae7931b2dc82)

![edit directoryindex](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/5d4f9f2d-b01b-47b0-82f9-fe2db46e1bcf)


> Reload apache for changes to take effect
```
sudo systemctl reload apache2
```
![sudo vim](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/718909b8-267f-4e97-9376-e08a5fb914c8)

> Edit /etc/apache2/mods-enabled/dir.conf file
```
vim /var/www/projectlamp/index.php
```

![vim create php](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/4f3830a1-bd28-4eca-aa97-022b47f00e34)


> edit index.php file
```
<?php
phpinfo();
```

![paste php code](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/3f279c83-2f4f-4a09-8f73-b10dc59c972f)


> Remove the file created
```
sudo rm /var/www/projectlamp/index.php
```

![remove vim](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/a16e8983-913f-4a9a-9e0f-3e6ea2a0a4d9)


## Creating a Virtual Host for your Website using Apache

### Step 4 - Creating a Virtual Host for your Website using Apache

> Create a domain called projectlamp
> Create a directory for projectlamp

```
sudo mkdir /var/www/projectlamp
```
> Assign Ownership of the directory with the USER
```
sudo chown -R $USER:$USER /var/www/projectlamp
```

![mk dir projectlamp](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/ec9b18c5-5a45-4afb-8711-eb89705bbbd6)


> Create and open a new configuration file in Apache's sites-available directory using your preferred command-line editor
```
sudo vi /etc/apache2/sites-available/projectlamp.conf
```
> Paste the bare-bone configuration by hitting on i on the keyboard.
```
<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

![paste bare-bone](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/1f0d985a-2f72-4483-9b74-7fa3228de6fa)

> use ls command to show the new file in the sites-available directory
```
sudo ls /etc/apache2/sites-available
```

![ls sites-available](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/9d600717-f2cf-4138-aa8d-4216b70d19e4)


> Use a2ensite command to enable the new virtual host
```
sudo a2ensite projectlamp
```

![enable projectlamp](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/c81044dc-cd13-4c08-bcde-95e74331885e)

> Disable Apache's default website
```
sudo a2dissite 000-default
```

![disable default Apache website](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/6274e759-d59b-49b6-9712-6ae6f3b74a88)

> Ensure configuration file contain no syntax error
```
sudo apache2ctl configtest
```

![syntax ok](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/ac42e179-828a-4e98-a150-f5a0484f2213)

> Reload Apache for changes to take effect
```
sudo systemctl reload apache2
```

![reload apache](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/64b3426f-29a8-42c6-b4ce-8ae60cf198b5)


> Create an index.html file in that location
```
sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html
```

![create index hmtl file](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/2f8dedce-2fc8-4eeb-a522-33fa111d764c)


> Open website through browser using Public IP
```
http://35.179.92.176:80
```

> Open website through browser using DNS
```
http://ec2-35-179-92-176.eu-west-2.compute.amazonaws.com:80
```

![open ip in browser](https://github.com/ArmstrongLiwox/DevOps/assets/143335106/bf3ab7ad-b0b4-4c72-959c-f3eb172a6828)



# THANK YOU
