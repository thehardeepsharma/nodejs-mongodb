Create Mongodb Service:

Step 1: Open an Administrator command prompt

Step 2: Create directories:

mkdir c:\mongodb\data\db
mkdir c:\mongodb\data\log


Step 3: Create a configuration file

Create a file C:\Program Files\MongoDB\Server\3.4\mongod.cfg wirth following content
systemLog:
    destination: file
    path: c:\data\log\mongod.log
storage:
    dbPath: c:\data\db
	
Step 4: Create the MongoDB service

sc.exe create MongoDB binPath= "\"C:\Program Files\MongoDB\Server\3.4\bin\mongod.exe\" --service --config=\"C:\Program Files\MongoDB\Server\3.4\mongod.cfg\"" DisplayName= "MongoDB" start= "auto"

If successfully created, the following log message will display
[SC] CreateService SUCCESS	

Step 5: Start the MongoDB service

net start MongoDB


Step 5: Stop the MongoDB service

net stop  MongoDB



For Open Mongo console
cd C:\Program Files\MongoDB\Server\3.4\bin
>mongo.exe