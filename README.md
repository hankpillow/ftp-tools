#### CHANGELOG ####
version: v0.1
- *download* command created.

version: v0.2
- *check-md5* report fixed. the average calculation was wrong.

version: v0.3
- ftp.config allowing multiples servers

version: v0.4
- *parse-config* created


FTP-TOOLS
=========

This is just a bunch os bash script to help doing ftp via command line.  
It's pretty much simple, basically it needs a ftp.config file in the same path as you call any script.  
To work fine, the target server must allow ssh access.  

#### Every script has its own helpers, so type "scriptname ?" and enjoy.####

##test-config##
*Tests/Creates the ftp.config* 
  
The ftp.config file is a simple text file in which you fill some server's fields.
The model is like this:  

[server1]  
hots=yourhost.com  
user=username  
root=/home/public_html/  
  
[server2]  
hots=yourhost2.com  
user=username2  
root=/home/static_html/ 
 
and so forth.

##connect##
*Just an alias to ssh using the ftp.config settings.*

##put##
*Deploy a file or an entire folder to the remote server.*  
ex: **put local-folder/. static/**  
ex: **put file-name static/bin/**

##download##
*Download a file or an entire folder from the remote server.*  
ex: **download remote-folder/. .**  

##local-md5##
*Runs the MD5 in every file in the given scope*  
ex: **local-md5 local-folder/**

##remote-md5##
*Runs the 'local-md5' in the remote server.*  
ex: **remote-md5 static/**

##check-md5##
*Compares the MD5 in the remote and local path and shows a report*  
ex: **check-md5 local-folder/ static/**

##run##
*Executes the given argument as script in the remote server.*  
ex: **run "ls -lR static/"**

##parse-config##
*A simple config parser.*  
ex: **parse-config file.conf env-name prop-name**

TO-DO:
------
- improve the ftp.config to allow connecting via specific ports.

INSTALL:
------
1. cd ~/bin
2. git clone git@github.com:hankpillow/ftp-tools.git
3. cd chmod +x ~/bin/ftp-tools
4. export PATH="~/bin/ftp-tools:${PATH}"