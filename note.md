docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=password123' -e 'MSSQL_PID=Express' -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-latest-ubuntu

# start the container
docker-compose up db

# use mssql cmd line locally
mssql -u SA -p Your_Password_123

# go into docker container and run mssql command line 
docker exec -it <CONTAINER_ID> /opt/mssql-tools/bin/sqlcmd -s localhost -U SA -P Your_Password_123


# you must use 'go' to execute the sql statement in the command line
1> select name from sys.sysdatabases;
2> go