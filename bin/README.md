#Following the explanation for all commands:

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

	* *The `[group] notation allows: `a-zA-Z0-9-_`*

	###usage:

	1. ####Getting groups:

		`$ parse-config file`

		Returns:

		```
		group-1
		group-2
		```

	2. ####Getting properties:

		`$ parse-config file group-1`

		Returns:

		```
		prop1
		prop2
		```

	3. ####Getting values:

		`$ parse-config file group-1 prop1 `

		Returns:

		```
		value1
		```

* ###test-config

	This script will check for a `remote.cfg` in the same scope the script was called and validate it.

	If the `remote.cfg` file was found a new one will be created.

	This script will check if all expected properties exists.

	They are:

	* `host` - server host. ie: `foo.server.com`
	* `port` - server port. ie: `123`
	* `user` - ssh user name. ie: `hank`.
	* `root` - the root path when connect. ex `/stage/foo/`. see [connect](#connect)
	* `bind` - to bind the host address (`ssh -L` way). ie: `8012:123.456.789.001:8034`

	If you won't use some properties, just let them empty. Missing properties will stop the execution.

* ###connect

	This script will first run [test-config](#test-config) then the proper script to connect via ssh.

* ###push

	Pushes a file/folder to the remote server.

	Considering the following `remote.cfg`

	```
	[stage]
	host=ftp.my-server.com
	port=
	user=user
	root=/www/
	bind=
	```

	1. ####Pushing single file:

		`$ push file1.txt`

	2. ####Pushing many files:

		`$ push file1.txt`

	3. ####Pushing folder:

		`$ push file1.txt`

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