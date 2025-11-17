# MySQL comparison between VM(self-managed) and Managed

## Recording
Loom recording <https://www.loom.com/share/6bf3424b9cfc4c339fdfcb416e5d5d3e> and <https://www.loom.com/share/d50e2c1923f34a93bfb87c2c53e8ce9a>
 
## Chosen platform
I decided to use google cloud platform to create the virtual machine and the cloud SQL database.

## VM
### VM creation
1. Select instance to create.
2. Choose E2 for price and usability.
3. Choose e2-small for 2GB of memory.
4. Choose Ubuntu OS system.
5. Everything else kept to default.

### Firewall configuration
1. Create a firewall rule.
2. Name it and give it a description.
3. Set IP range to 0.0.0.0/0 to allow all IPs.
4. Set protocol to tcp:3306

### SSH steps
1. Input `sudo apt-get update` to update the OS system.
2. Input `sudo apt install mysql-server mysql-client` to install mysql into the server.
3. Input `sudo mysql` to log in into mysql.
4. Input `CREATE USER 'xxx'@'%' IDENTIFIED BY 'xxx';` to add user to database
5. Input `GRANT ALL PRIVILEGES ON *.* TO 'xxx'@'%' WITH GRANT OPTION;` to give all privileges to the user.
6. Edit mysqld.cnf file and input `0.0.0.0/0` to allow for other network connections.
7. Researt SSH and input `mysql -u dba -p` to locally test the user connection to mysql.
8. Input the password you set to the username.

Secrets can be stored in an .env file

## Managed Cloud SQL
### Cloud SQL
1. Select to create a sandbox MySQL instance.
2. Name instance and set a password.
3. Select a region press create.

### Configuration
1. Add `0.0.0.0/0` to authorized networks.
2. Disable SSL only connection for security.
3. Add a new user with a username and set a password for it.

Secrets can be stored in an .env file

## Screenshots
### VM
Running VM
![VM run](screenshots/vm/running.png)

VM configuration
![VM config](screenshots/vm/vm_config1.png)

SSH connection to MySQL
![general ssh](screenshots/vm/generalssh.png)

Python script results
![VM python](screenshots/vm/vm_python.png)

VM query
![VM query](screenshots/vm/vm_query.png)

### Managed
Running MN cloud SQL
![MN run](screenshots/managed/running.png)

Python script results
![MN python](screenshots/managed/managed_python.png)

MN cloud SQL query
![MN query](screenshots/managed/query.png)
