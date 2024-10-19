### Installation
[MongoDb Installation on Amazon Web Services AWS EC2 Ubuntu OS](https://medium.com/@johnmark_76235/mongodb-installation-on-amazon-web-services-ec2-ubuntu-os-060c8a6bf7d2)

### Remote Connection
[MongoDB Remote Connection on a VPS server with MongoDB Compass](https://medium.com/@johnmark_76235/mongodb-remote-connection-with-mongodb-compass-1af3d13a349a)

### Backup
[MongoDB Backup](https://medium.com/@johnmark_76235/mongodb-backup-70ae4961f274)

### Show Databases, Collections (tables) and Table Columns
```vim
test> show databases; #or show dbs;
test> show collections; #or show tables;
test> db.test.findOne(); #show Collection columns
```
### Create User Admin in Admin Database
```vim
$ mongosh;
$ use admin;
$ admin> db.createUser({
        user:"AdminUsername",
        pwd:"AdminPassword",
        roles:[{ role:"root",db:"admin" }]
    });
```
### Create Database and Create a User
```vim
$ use test; #Create user and Select database
$ db.createUser({
    user: "tester",
    pwd: "tester123",
    roles: [ { role: "readWrite", db: "test" } ]
  });
```
### Login Account
```vim
$mongosh --username admin --authenticationDatabase admin
```
### Remote Connection String
```vim
mongodb://tester:tester123@162.220.160.183:27017/?authSource=test
```
### MongoDb Consuming Large Memory
Add the wiredTiger configuration
```vim
storage:
  wiredTiger:
   engineConfig:
       cacheSizeGB: 0.256 #256 memory
```
