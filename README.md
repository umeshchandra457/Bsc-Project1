###Computer Architecture and System - Project and learning Journals

## Introduction

The aim of the project is to install the virtual machine and configure the virtual machine hosting LAMP stack and to demonstrate the web application on it.The other three main stages of the installation can be as follows,

The initial configuration of the virtual machine and the installation of the operating system (Linux Ubuntu).
Installation and the tresting of the Apache web browser, MYsql database and php processing module.
Insatllation and the testing of CMS and modification of hosted content.
Configuration and Deployment Virtual Machine

 ## Virtualisation and virtual machine
 
Virtualisation is a process of creating a software or the virtual representation of the software rather than the physical one. Virtualisation can also be apply to the server, applications, storage and the networks to increase the efficiency and reduce the expenses of the networks. Virtualisation can also uses the software to stimulate the existing hardware and create the virtual machine.

###The installation process for the VM Virtual box involving of different steps;

The first thing is to install the virtual machine
Install the operating system on the virtual machine
Execute the and run the commands on the operating system on virtual machine.
The next step is to download the virtual box and install the virtual machine in the system. The after installation a window will open up the virtual machine. After installation of step by step process its automatically popping up the new virtual machine dialogue box will open if not click on the new button to create a new virtual machine.

The first step is to enter the name of the operating system which you wish to set up and then select the operating system ‘Linux’ and the select the version which you want to use that is Ubuntu 32 bit or the Ubuntu 64 bit.
- The next step is to select the memory size of the Ram that we are going to allocate to the virtual machine that is 1024 MB. 
- Then after select next and here you select the hard disk for the that going to use for the virtual machine, so create a new virtual hard disk is about 20 GB, if you have enough memory but the recommended memory is 8 GB. 
- And then select the file type that as virtual hard disk (VHD) using for the virtual machine and then click next and then select the location and the file that would virtual machine that will store in the hard disk and click create.

After creating the virtual machine, a window pop ups automatically, or if not click on the start button to start the virtual machine manually. But when start it up t couldn’t load the bootable file because the Ubuntu file isn’t it stored in the virtual machine, for that we need to download the Ubuntu file.

Download the latest version of the Ubuntu file from the link www.ubuntu.com/download/desktop.

Open the VM Virtual box

- Click on the newly created VM and then go to settings, from the settings click on the storage then you will get storage tree, in the      storage tree click on the disk icon “empty”.
- Click on the small disk on the right of the field under the attributes on the right side of the window.
   Locate the file were you download the Ubuntu file from the Ubuntu website.
- Click the ok button and then its return to the main window of the virtual machine.
   Concept of Web servers

Web servers are the computer systems or the programmes that hosts the web sites by using the Http(Hypertext transfer protocol) to server the files from a webpages when the users are requests that which are forwarded by their computers http clients. All the system that host web sites must web server. Now the leading web server is Apache which is most widely used web server, and the Microsoft internet information server (IIS). Web servers are often come as large packages of internet programing which serving emails, downloading request for file protocol transfer, images and build to publishing the web pages. Choosing the web server and which include how well it works on the operating system and ability to handle the server programming, security characteristics and publishing the search engine and web sites are take into consideration.

##Apache Web servers

Apache is web server that widely used web server in the software. Apache server is developed and maintained by the apache software foundation, which is developed by a group of programmers. Apache is an open source software that are available for free. Apache runs 67% on the all web server in the world. Apache servers are the highly customized to meet the needs of the different environment by using extensions and the modules.

##Set and configuration of Apache web server

The steps involved in the installation of the Apache server on already created and deployed the Ubuntu server. First we are going to install the apache server on the already installed Ubuntu server. Login into the Vm virtual machine with the username and the password that you have created during the installation of the Ubuntu on the virtual machine. Then first check the updates if any updates are available by using the update commands. After checking for the all updates then it’s time to install the apache web server by entering the installation command.

We want to change the settings to apache web server then we will start our booting our system. For the system to boot enter the systemctl enable commands to enable the service. Then after to start the service of the apache server then enter the systemctl start commands to start the apache web server.

After that lets check the apache server is running. First thing need to check the adapter setting make it visible on the host, then need to shut down the Vm and change the setting on our network adapter. By default it should change to NAT(Network adapter translation) and then we can set up a port forwarding by host by selecting settings and then network, select advance button then change the host port to 80 and guest port to 80 and click ok. Then should check that your localhost is working on the web browser or not. For that enter http://www.localhost:80 then you will get the web page apache2 Ubuntu has default page if the it configure correctly. Now the apache web server setup and configured.

##Installation of MySQL

MySQL is open source relational data base. It has very important features of modern websites to maintain the database for users’ data. To install the MySQL database server enter the following commands.

-sudo apt-get install mysql-client mysql-server

As our database are not that secure, for that reason enter the following command for harden the security sudo mysql_secure_installation.

First it will ask for the validate the password plugin so enter ‘yes’ and then press enter and chose the password length and ask for the root password but recommended not to change the password. Then change to load the privileges table and the changes take effect now.

##Installation of PHP and modules

The last thing to install is php and the modules for work with the web and the database servers by using the commands

-Sudo apt-get install php7.0 php7.0-mysql libapache –mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd

Then to test the php is working with the collaboration with the web server then create info. Php file inside the var/www//html:

-Sudo vi /var/www/html/info. Php

Then press i key to enter the insert mode and then type

- Then press esc to after finishing and then enter the command: wq to save the file and exit Vi. Now open the browser on the host computer by address localhost/info.php then will get the configuration page if the installation done correctly.

Now we have our lamp stack set up and going to install content management system. It is use for the computer applications which support for creating and editing the digital pages. We are going to install the world most cms is WordPress open source. CMS are designed to create and run websites.

To install the WordPress enter the different command to download latest WordPress package from repository. After the download then it needs to extract the files from compressed folder by using the extract command tar –xzvf latest.tar.gz, then needs to move all the contents of WordPress folder to default apache root directory by using the command. Finally set the permission on the web site directory that’s give the ownership of word file to the web server.

Then change permissions to allow anyone to read and execute the file.

##Create Mysql for database for WordPress

Before need to run set up mysql for WordPress by entering the command to open mysql mysql –u root –p and then enter the following commands to create the data base, username and the password for the word press and then after entering the all flush the privileges and then exit. Then to restart the apache and mysql server by entering the command Sudo systemctl restart apache2.srevice and sudo systemctl restart mysql.service and to check the WordPress is opening by enter the command http://localhost:80/wp-admin.php, then

Its open the word press web page enter the data base name, user name and the password created on the word press data base, then after it request to change the password as you wish and login into the WordPress web page. Now you are on the word press web page to check wheather the web pages are working on the local host go to the pages and then click on the link then it will directly open up the project that your created, with these complete the creation of the word press project.

##Reflection

During the installation of the Virtual machine I got the difficulties when installing the Ubuntu on the virtual machine and also apache server, when everything was installed and I try to check the localhost on the browser I didn’t get the apache web page and tried few times by checking the process. Then I got stuck during the login in the word press page I quite enter the username and the password wrong, tried few times to login onto the word press web page.

##Conclusion

By accomplishing goal by installing the Ubuntu server on the virtual machine and creating the web pages for the LAMP stack and also creating the word press and making a web page on word press correctly.
