### Installation
[MongoDb Installation on Amazon Web Services AWS EC2 Ubuntu OS](https://medium.com/@johnmark_76235/mongodb-installation-on-amazon-web-services-ec2-ubuntu-os-060c8a6bf7d2)

### Remote Connection
[MongoDB Remote Connection on a VPS server with MongoDB Compass](https://medium.com/@johnmark_76235/mongodb-remote-connection-with-mongodb-compass-1af3d13a349a)

### Backup
[MongoDB Backup](https://medium.com/@johnmark_76235/mongodb-backup-70ae4961f274)

### Create User Admin in Admin Database
```vim
$ mongosh;
$ use admin;
$ admin> db.createUser(
    {user:"AdminUsername",
    pwd:"AdminPassword",
    roles:[{ 
        role:"root",db:"admin" }]
        });
```
### Test Admin Account
```vim
$mongosh --username admin --authenticationDatabase admin
```
### Create User in a Database
```vim
$ use test;
$ db.createUser(
  {
    user: "tester",
    pwd: "tester123",
    roles: [ { role: "readWrite", db: "test" } ]
  }
)
```
### Remote Connection String
```vim
mongodb://tester:tester123@162.220.160.183:27017/?authSource=test
```
