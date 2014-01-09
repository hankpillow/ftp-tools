###Following the explanation for all commands:

* ##parse-config

	This script will parse a given config file and return the values accordingly to the arguments you provide.

	The file must follow the model:

	```
	[group-1]
	prop1=value1
	prop2=value2

	[group-2]
	prop1=value3
	prop2=value4
	```



	* *The "[group]" notation allows: `a-zA-Z0-9-_`*

	###usage:

	1. ####Getting groups:

		```
		$ parse-config file
		```

		Returns:

		```
		group-1
		group-2
		```

	2. ####Getting properties:

		```
		$ parse-config file group-1
		```

		Returns:

		```
		prop1
		prop2
		```

	3. ####Getting values:

		```
		$ parse-config file group-1 prop1
		```

		Returns:

		```
		value1
		```

* ###test-config

	The ftp.config file is a simple text file in which you fill some server's fields.	The expected format for this document is:

	```
	[server1]
	hots=yourhost.com
	user=username
	root=/home/public_html/

	[server2]
	hots=yourhost2.com
	user=username2
	root=/home/static_html/
	```

	Allowed properties

* ###connect

	Just an alias to ssh using the ftp.config settings

* ###put

	Deploy a file or an entire folder to the remote server.*

	```
	$ put local-folder/. static/
	```

	Or

	```
	$ put file-name static/bin/
	```
* ###download

	Download a file or an entire folder from the remote server.*

	```
	$ download remote-folder/. .
	```

* ###local-md5

	Runs the MD5 in every file in the given scope*

	```
	$ local-md5 local-folder/**
	```

* ###remote-md5

	Runs the 'local-md5' in the remote server.

	```
	$ remote-md5 static/**
	```

* ###compare-md5

	Compares the MD5 in the remote and local path and shows a report

	```
	$ check-md5 local-folder/ static/**
	```

* ###run

	Executes the given argument as script in the remote server.

	```
	$ run "ls -lR static/
	```