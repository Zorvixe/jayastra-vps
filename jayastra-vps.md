ssh root@147.93.103.224


```
CREATE USER jayastrauser WITH ENCRYPTED PASSWORD 'jayastrapassword';

```

```

CREATE DATABASE jayastradb OWNER jayastrauser;

```

```

GRANT ALL PRIVILEGES ON DATABASE jayastradb TO jayastrauser;

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

```bash
ln -s /etc/nginx/sites-available/jayastra.in.conf /etc/nginx/sites-enabled/
```

```bash
 ln -s /etc/nginx/sites-available/app.jayastra.in.conf /etc/nginx/sites-enabled/
```

```bash
ln -s /etc/nginx/sites-available/api.jayastra.in.conf /etc/nginx/sites-enabled/
```

```
certbot --nginx -d jayastra.in -d www.jayastra.in -d app.jayastra.in -d api.jayastra.in

```
