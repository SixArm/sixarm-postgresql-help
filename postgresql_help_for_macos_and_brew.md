# PostgreSQL help for macOS and brew

Verify PostgresSQL installed and at least version 9.6.

    $ brew info postgresql
    postgresql: stable 9.6.1 (bottled), HEAD
    ...

Verify there is a Cellar:

    $ ls /usr/local/Cellar/postgresql
    9.6.1

Verify the postgres directory exists and is correctly owned by admin:

    $ ls -ladg /usr/local/var/postgres
    drwxr--r--  2 admin  68 Dec  5 03:20 /usr/local/var/postgres

Do you have a conflict with Postgres.app?

   $ ls /Applications/Postgres.app
   $ ls ~/Applications/Postgres.app

Verify Postgres is running:

    $ ps auxwww | grep post

Verify you can connect:

    $ psql -U postgres

Verify you can start:

    $ postgres -D /usr/local/var/postgres

Nuclear option: totally delete all the existing databases, then recreate a fresh one:

    $ rm -rf /usr/local/var/postgres
    $ initdb /usr/local/var/postgres -E utf8
    $ /usr/local/Cellar/postgresql/9.6.1/bin/createuser -s postgres
    $ pg_ctl -D /usr/local/var/postgres -l logfile start
