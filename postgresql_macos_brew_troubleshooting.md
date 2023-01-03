# PostgreSQL macOS brew troubleshooting


### Verify brew formula

List:

```sh
% brew list --version postgresql
postgresql@14 14.6
```

Verify version:

```sh
% brew info postgresql@14
==> postgresql@14: stable 14.6 (bottled)
```


### Verify brew cellar

Where does brew expect to find postgres?

```sh
% brew --cellar postgresql@14
/opt/homebrew/Cellar/postgresql@14
```

Verify the cellar directory exists:

```sh
% ls $(brew --cellar postgresql@14)
14.6
```

Save the info for our next steps:

```sh
% cellar=$(brew --cellar postgresql@14)
% version=$(brew list --version postgresql | head -1 | awk '{print $2}')
% path="$cellar/$version"
% echo $path
/opt/homebrew/Cellar/postgresql@14/14.6
```


### Verify postgres directory

Verify the postgres directory exists and is correctly owned by admin:

    $ ls -ladg /usr/local/var/postgres
    drwxr--r--  2 admin  68 Dec  5 03:20 /usr/local/var/postgres

Verify there is a plist file:

    $ ls /usr/local/opt/postgresql/*.plist
    /usr/local/opt/postgresql/homebrew.mxcl.postgresql.plist

Do you have a conflict with Postgres.app?

   $ ls /Applications/Postgres.app
   $ ls ~/Applications/Postgres.app

Verify Postgres is running:

    $ ps auxwww | grep post

Verify you can connect:

    $ psql -U postgres

Verify you can start:

    $ postgres -D /usr/local/var/postgres


### Verify postgres user

Verify the postgres user exists:

```sh
% $path/bin/createuser -s postgres
createuser: creation of new role failed: ERROR:  role "postgres" already exists
```


## Nuclear option

Totally delete all the existing databases, then recreate a fresh one:

    $ rm -rf /usr/local/var/postgres
    $ initdb /usr/local/var/postgres -E utf8
    $ /usr/local/Cellar/postgresql/9.6.1/bin/createuser -s postgres
    $ pg_ctl -D /usr/local/var/postgres -l logfile start
    $ psql postgres -c 'CREATE EXTENSION "adminpack";'
    $ psql -U postgres

Optional setup to launch automatically:

    $ mkdir -p ~/Library/LaunchAgents
    $ ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents
    $ launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist
