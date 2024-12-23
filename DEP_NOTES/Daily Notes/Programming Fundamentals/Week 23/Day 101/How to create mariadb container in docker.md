link -> https://hub.docker.com/_/mariadb

First pull mariadb image

`docker pull mariadb`

Then create the maria db container -> 

`docker run -e MARIADB_ROOT_PASSWORD=mariasql -p 5000:3306 -v ~/mariadb:/var/lib/mariadb mariadb
`

