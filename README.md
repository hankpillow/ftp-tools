FTP-TOOLS
=========

This is just a bunch os bash script to help doing ftp via command line.  
It's pretty much simple, basically it needs a ftp.config file in the same path as you call any script.  
To work fine, the target server must allow ssh access.  

#### Every script has its own helpers, so type "scriptname ?" and enjoy.####

##test-config##
*Tests/Creates the ftp.config*

connect
-------
*Just an alias to ssh using the ftp.config settings.*

put
-----
*Deploy a file or an entire folder to the remote server.*  
ex: **put local-folder/. static/**  
ex: **put file-name static/bin/**

local-md5
---------
*Runs the MD5 in every file in the given scope*  
ex: **local-md5 local-folder/**

remote-md5
----------
*Runs the 'local-md5' in the remote server.*  
ex: **remote-md5 static/**

check-md5
-----------
*Compares the MD5 in the remote and local path and shows a report*  
ex: **check-md5 local-folder/ static/**

run
-----------
*Executes the given argument as script in the remote server.*  
ex: **run "ls -lR static/"**


TO-DO:
------
- improve the ftp.config to allow multiples remote servers for the purpose of tests and final deploying.
- improve the ftp.config to allow connecting via specific ports.

INSTALL:
------
1. cd ~/bin
2. git clone git@github.com:hankpillow/ftp-tools.git
3. cd chmod +x ~/bin/ftp-tools
4. export PATH="~/bin/ftp-tools:${PATH}"