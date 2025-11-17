# Setup steps for managed MySQL
## Cloud SQL
1. Select to construct a sandbox MySQL instance.
2. Create an instance name and password.
3. Select a region and then press the Create button.

## Configurate
1. Add the IP address '0.0.0.0/0' to the list of allowed networks.
2. To ensure security, disable SSL-only connections.
3. Create a new user with a username and password.

## Problems/RoadBlocks
1. At first, I tried connecting to the database externally using the connection name. However, I got the public IP address and utilized it to access to the database.

## Setup Time
It took roughly 15 minutes to create the database, connect to the Python script, and run a query to ensure that the script was working properly.
