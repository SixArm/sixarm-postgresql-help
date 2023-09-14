# PostgreSQL Debian clusters

Install:

```sh
sudo apt update
sudo apt -y install postgresql-12 postgresql-client-12
```

Status:

```sh
systemctl status postgresql.service 
systemctl status postgresql@12-main.service 
```

Cluster:

```sh
sudo pg_lsclusters
sudo pg_ctlcluster 12 main start
```
