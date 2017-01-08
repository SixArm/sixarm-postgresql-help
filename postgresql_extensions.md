# PostgreSQL extensions

See https://www.postgresql.org/docs/current/static/contrib.html

We use these extensions:

  * [adminpack](http://www.postgresql.org/docs/current/static/dblink.html): administration and management tools
  * [dblink](http://www.postgresql.org/docs/current/static/dblink.html): connect to other databases
  * [hstore](http://www.postgresql.org/docs/current/static/hstore.html): hstore for storing sets of key-value pairs
  * [intarray](http://www.postgresql.org/docs/current/static/intarray.html): integer array functions and operators
  * pgcrypto
  * [postpic](http://github.com/drotiro/postpic): image processing
  * [postgis](http://postgis.refractions.net/): geographic information system
  * [prefix](http://pgfoundry.org/projects/prefix): prefix matching for text searh
  * [pgsphere](http://pgsphere.projects.postgresql.org/): spherical coordinates
  * [multicorn](http://multicorn.org/): link to other systems to retrieve data via Foreign Data Wrappers (FDWs).
  * [uuid-ossp](https://www.postgresql.org/docs/current/static/uuid-ossp.html): generate universally unique identifiers (UUIDs)
  * [xml2](https://www.postgresql.org/docs/current/static/xml2.html): XML XPath querying and XSLT functionality


To create:

    psql postgres -c 'CREATE EXTENSION "adminpack";'
    psql postgres -c 'CREATE EXTENSION "dblink";'
    psql postgres -c 'CREATE EXTENSION "hstore";'
    psql postgres -c 'CREATE EXTENSION "intarray";'
    psql postgres -c 'CREATE EXTENSION "pgcrypto";'
    psql postgres -c 'CREATE EXTENSION "postgis";'
    psql postgres -c 'CREATE EXTENSION "postpic";'
    psql postgres -c 'CREATE EXTENSION "prefix";'
    psql postgres -c 'CREATE EXTENSION "pgsphere";'
    psql postgres -c 'CREATE EXTENSION "multicorn";'
    psql postgres -c 'CREATE EXTENSION "uuid-ossp";'
    psql postgres -c 'CREATE EXTENSION "xml2";'
