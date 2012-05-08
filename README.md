FTP-TOOLS
=========

This is just a bunch os bash script to help doing ftp via command line.

It's pretty much simple, basically it needs a ftp.config file in the same path as you call any of these script.

test-config
-----------
Tests/Creates the ftp.config

connect
-------
Just an alias to ssh using the ftp.config settings.

put
-----
Deploy a file or an entire folder to the remote server.

local-md5
---------
Runs the MD5 in every file in the given scope

remote-md5
----------
Runs the 'local-md5' in the remote server.

check-md5
-----------
Compares the MD5 in the remote and local path and shows a report


*Every script has its own helpers, so, type "scriptname ?" and enjoy.*

TO-DO:
------
- improve the ftp.config to allow multiples servers remote servers for the purpose of test servers and final deploying.

INSTALL:
------
- cd ~/bin
- git clone git@github.com:hankpillow/ftp-tools.git
- cd chmod +x ~/bin/ftp-tools
- export PATH="~/bin/ftp-tools:${PATH}"