# cms-sandbox

A docker-compose config for testing out several CMSes.

At present, the config will set up a shared mariadb database (MySQL-like), and instances of WordPress (port 8001), Joomla (port 8002), Drupal  (port 8003), and ghost  (port 8004).

## Setting up for the first time...

Both WordPress and Joomla rely on the database being present, so it helps to let it completely set up first before spinning everything else up:

```shell
docker-compose up --no-color -d db
```

... and after the database is ready:

```shell
docker-compose up --no-color -d
```

## Other notes

The experience would be better if the config files for the various CMS helped with the initial setup, but they're all relatively decent as is.  Do note that you need to tell Joomla that the MySQL host is `mysql`, not `localhost`, and that the database root user is `root`, with password `root-password`.
