# Setup steps for vm MySQL
## VM creation
1. Choose an instance to create.
2. Choose E2 based on pricing and utility.
3. Select e2-medium with a minimum of 4GB of RAM.
4. Choose the Ubuntu operating system.
5. Everything else was left to default.

## Firewall configuration
1. Add a firewall rule.
2. Give it a name and description.
3. Set the IP range to 0.0.0.0/0 to enable all IP addresses.
4. Set the protocol to tcp:3306.

## SSH steps
1. Run'sudo apt-get update' to upgrade the operating system.
2. Run'sudo apt install mysql-server mysql-client' to install MySQL on the server.
3. Type'sudo mysql' to log in to MySQL.
4. Enter 'CREATE USER 'xxx'@'%' IDENTIFIED BY 'xxx';' to add the user to the database.
5. Enter 'GRANT ALL PRIVILEGES ON *.* TO 'xxx'@'%' WITH GRANT OPTION;' to grant the user full privileges.
6. In the mysqld.cnf file, enter '0.0.0.0/0' to allow for more network connections.
7. Restart SSH and type'mysql -u dba -p' to locally test the user connection to MySQL.
8. Enter the password you set for the username.

## Roadblocks/Problem
1. When prompted for the password to log into the mysql database, there was not input showing when typing anything. Searched it up and found out that this was a safety feature to protect passwords.

## Setup Time
1. It took about 30-40 minutes to create the VM, configure it, install MySQL, execute the Python script, and run a query within the VM.
