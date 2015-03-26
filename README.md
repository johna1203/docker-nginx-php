# nginx + php


## Prepare the container for data

```shell

$ docker run --name="nginx-php-data" johna1203/docker-data

```

To share the container directory with your localhost, use the -v option

```shell

$ mkdir ~/src/nginx-data

$ docker run --name="nginx-php-data" -v ~/src/nginx-data:/data johna1203/docker-data

```

## Create the container nginx + php

```shell

$ docker run -d --name="nginx-php" --volumes-from=nginx-php-data -p 8080:80 johna1203/docker-nginx-php

```

## Run <?php phpinfo() ?>

```shell

$ cd ~/src/nginx-data/http
$ echo "<?php phpinfo();" > index.php

```

Now access the browser using port 8080

if you are using boot2docker

check the IP using this command.

```shell

$ boot2docker ip
192.xxx.xxx.xxx

```

if using boot2docker

http://192.xxx.xxx.xxx:8080

if not

http://localhost:8080

Thank U
