```
postgres=# CREATE USER jayastrauser WITH ENCRYPTED PASSWORD 'jayastrapassword';

```

```

postgres=# CREATE DATABASE jayastradb OWNER jayastrauser;

```

```

postgres=# GRANT ALL PRIVILEGES ON DATABASE jayastradb TO jayastrauser;

```

```

root@srv973760:/var/www/jayastra# psql -d jayastradb -U jayastrauser

```

```

DATABASE_URL=postgresql://jayastrauser:jayastrapassword@127.0.0.1:5432/jayastradb

```

```
 nano /etc/nginx/sites-available/jayastra.in.conf

```

```
 nano /etc/nginx/sites-available/app.jayastra.in.conf
```

```

nano /etc/nginx/sites-available/api.jayastra.in.conf

```

```
root@srv973760:/var/www/jayastra/frontend# certbot --nginx -d jayastra.in -d www.jayastra.in -d app.jayastra.in -d api.jayastra.in

```