# PostgreSQL extensions

See https://www.postgresql.org/docs/current/static/contrib.html

We use these extensions:

  * [adminpack](http://www.postgresql.org/docs/current/static/dblink.html): administration and management tools.
  * [auth_delay](https://www.postgresql.org/docs/current/static/auth-delay.html): authentication delay to make password attacks harder.
  * [auto_explain](https://www.postgresql.org/docs/current/static/auto-explain.html): automatically explain execution plans of slow statements.
  * [bloom](https://www.postgresql.org/docs/current/static/bloom.html): bloom filter data structure to test whether an element is in a set.
  * [citext](https://www.postgresql.org/docs/current/static/citext.html): case-insensitive character string type, citext.
  * [cube](https://www.postgresql.org/docs/current/static/cube.html): cube data type for representing multidimensional space.
  * [dblink](http://www.postgresql.org/docs/current/static/dblink.html): connect to other databases.
  * [dict_xsyn](https://www.postgresql.org/docs/current/static/dict_xsyn.html): extended synonym dictionary for full-text search.
  * [earthdistance](https://www.postgresql.org/docs/current/static/earthdistance.html): calculate great circle distances on the surface of the Earth.
  * [file_fdw](https://www.postgresql.org/docs/current/static/file_fdw.html): file foreign-data wrapper for the server's file system.
  * [fuzzystrmatch](https://www.postgresql.org/docs/current/static/fuzzystrmatch.html): fuzzy string match functions for full-text search.
  * [hstore](http://www.postgresql.org/docs/current/static/hstore.html): hstore for storing sets of key-value pairs.
  * [intarray](http://www.postgresql.org/docs/current/static/intarray.html): integer array functions and operators.
  * [lo](https://www.postgresql.org/docs/current/static/lo.html): large object support.
  * [ltree](https://www.postgresql.org/docs/current/static/ltree.html): label tree data type for hierarchical tree-like structures.
  * [multicorn](http://multicorn.org/): link to other systems to retrieve data via Foreign Data Wrappers (FDWs).
  * [pg_stat_statements](https://www.postgresql.org/docs/current/static/pgstatstatements.html): track execution statistics of all SQL statements executed by a server.
  * [pg_trgm](https://www.postgresql.org/docs/current/static/pgtrgm.html]: trigram matching for text search.
  * [pgcrypto](https://www.postgresql.org/docs/current/static/pgcrypto.html): cryptographic functions.
  * [pgsphere](http://pgsphere.projects.postgresql.org/): spherical coordinates.
  * [pgstattuple](https://www.postgresql.org/docs/current/static/pgstattuple.html): tuple statistics functions.
  * [postgis](http://postgis.refractions.net/): geographic information system.
  * [postpic](http://github.com/drotiro/postpic): image processing.
  * [postgres_fdw](https://www.postgresql.org/docs/current/static/postgres_fdw.html): foreign-data wrapper for external PostgreSQL servers.
  * [prefix](http://pgfoundry.org/projects/prefix): prefix matching for text searh.
  * [seg](https://www.postgresql.org/docs/current/static/seg.html): seg data type for representing line segments or intervals.
  * [tablefunc](https://www.postgresql.org/docs/current/static/tablefunc.html): table functions.
  * [uuid-ossp](https://www.postgresql.org/docs/current/static/uuid-ossp.html): generate universally unique identifiers (UUIDs).
  * [unaccent](https://www.postgresql.org/docs/current/static/unaccent.html): filtering text search dictionary that removes accents (diacritic signs) from lexemes.
  * [xml2](https://www.postgresql.org/docs/current/static/xml2.html): XML XPath querying and XSLT functionality.

We skip these additional supplied modules:

  * [btree_gin](https://www.postgresql.org/docs/current/static/btree-gin.html): b-tree GIN operator for fast search testing.
  * [btree_gist](https://www.postgresql.org/docs/current/static/btree-gist.html): b-tree GIST operator for fast search testing.
  * [chkpass](https://www.postgresql.org/docs/current/static/chkpass.html): check passwords using simple encryption.
  * [dict_int](https://www.postgresql.org/docs/current/static/dict_int.html): dictionary integer search example.
  * [intagg](https://www.postgresql.org/docs/current/static/intagg.html): integer aggregator and an enumerator; now obsolete.
  * [isn](https://www.postgresql.org/docs/current/static/isn.html): international standard numbering for products.
  * [pageinspect](https://www.postgresql.org/docs/current/static/pageinspect.html):  inspect the contents of database pages at a low level.
  * [passwordcheck](https://www.postgresql.org/docs/current/static/passwordcheck.html): check every password to ensure it's strong.
  * [pg_buffercache](https://www.postgresql.org/docs/current/static/pg_buffercache.html): examine the shared buffer cache in real time.
  * [pg_freespacemap](https://www.postgresql.org/docs/current/static/pg_freespacemap.html): examine the free space map (FSM).
  * [pg_prewarm](https://www.postgresql.org/docs/current/static/pg_prewarm.html): pre-warm a buffer cache.
  * [pgrowlocks](https://www.postgresql.org/docs/current/static/pgrowlocks.html): show row locking information for a specified table.
  * [pg_visibility](https://www.postgresql.org/docs/current/static/pg_visibility.html): examine the visibility map (VM).
  * [sepgsql](https://www.postgresql.org/docs/current/static/sepgsql.html):  label-based mandatory access control (MAC) based on SELinux security policy.
  * [sslinfo](https://www.postgresql.org/docs/current/static/sslinfo.html): SSL certificate information for the current client connection.
  * [spi](https://www.postgresql.org/docs/current/static/spi.html): server programming interface (SPI) examples for triggers.
  * [tcn](https://www.postgresql.org/docs/current/static/tcn.html): trigger change notification function for table listeners.
  * [test_decoding](https://www.postgresql.org/docs/current/static/test_decoding.html): example of a logical decoding output plugin.
  * [tsearch2](https://www.postgresql.org/docs/current/static/tsearch2.html): text search functionality; deprecated.
  * [tsm_system_rows](https://www.postgresql.org/docs/current/static/tsm_system_rows.html): table sampling method SYSTEM_ROWS.
  * [tsm_system_time](https://www.postgresql.org/docs/current/static/tsm_system_time.html): table sampling method SYSTEM_TIME.

We use this code to create the exenstions:

    psql postgres -c 'CREATE EXTENSION "adminpack";'
    psql postgres -c 'CREATE EXTENSION "authdelay";'
    psql postgres -c 'CREATE EXTENSION "auto_explain";'
    psql postgres -c 'CREATE EXTENSION "bloom";'
    psql postgres -c 'CREATE EXTENSION "citext";'
    psql postgres -c 'CREATE EXTENSION "cube";'
    psql postgres -c 'CREATE EXTENSION "dblink";'
    psql postgres -c 'CREATE EXTENSION "dict_xsyn;'
    psql postgres -c 'CREATE EXTENSION "earthdistance;'
    psql postgres -c 'CREATE EXTENSION "file_fdw;'
    psql postgres -c 'CREATE EXTENSION "fuzzystrmatch;'
    psql postgres -c 'CREATE EXTENSION "hstore";'
    psql postgres -c 'CREATE EXTENSION "intarray";'
    psql postgres -c 'CREATE EXTENSION "lo;'
    psql postgres -c 'CREATE EXTENSION "ltree;'
    psql postgres -c 'CREATE EXTENSION "multicorn";'
    psql postgres -c 'CREATE EXTENSION "pg_stat_statements";'
    psql postgres -c 'CREATE EXTENSION "pg_trgm";'
    psql postgres -c 'CREATE EXTENSION "pgcrypto";'
    psql postgres -c 'CREATE EXTENSION "pgsphere";'
    psql postgres -c 'CREATE EXTENSION "pgstattuple";'
    psql postgres -c 'CREATE EXTENSION "postgis";'
    psql postgres -c 'CREATE EXTENSION "postgres_fdw";'
    psql postgres -c 'CREATE EXTENSION "postpic";'
    psql postgres -c 'CREATE EXTENSION "prefix";'
    psql postgres -c 'CREATE EXTENSION "seg";'
    psql postgres -c 'CREATE EXTENSION "tablefunc";'
    psql postgres -c 'CREATE EXTENSION "unaccent";'
    psql postgres -c 'CREATE EXTENSION "uuid-ossp";'
    psql postgres -c 'CREATE EXTENSION "xml2";'

Add to `postgresql.conf` file:

    shared_preload_libraries = 'auth_delay'
    auth_delay.milliseconds = '500'
