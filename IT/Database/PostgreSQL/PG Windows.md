- To create a new PostgreSQL instance, you'll need to run the `initdb` command with the `--pgdata` option specifying the data directory and the `--locale` option specifying the locale.
- Open a command prompt with administrative privileges and navigate to the PostgreSQL bin directory. 
	- This directory is typically located in the PostgreSQL installation directory under the "bin" sub-folder (e.g., `C:\Program Files\PostgreSQL\<version>\bin`).
- Run the following command to initialize a new PostgreSQL instance:

`initdb --pgdata=C:\path\to\data\directory --locale=en_US.utf8`

Replace `C:\path\to\data\directory` with the desired location for the data directory.

After initializing the instance, you can start it using the `pg_ctl` command. Navigate to the PostgreSQL installation directory and run:

`pg_ctl start -D C:\path\to\data\directory -o "-p <port>"`

Replace `<port>` with the desired port number.
Access the new PostgreSQL instance using a PostgreSQL client (such as `psql` or `pgAdmin`) and connecting to the specified port.
Remember that managing multiple PostgreSQL instances on Windows involves keeping track of different data directories and port numbers for each instance.