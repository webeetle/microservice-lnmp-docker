# Introduction

Deploy a LNMP (Linux, Nginx, MySQL, PHP7) micro-service using docker.

### Architecture

![webeetle_lnmp_architecture][1]

The whole app is divided into three Containers:

1. Nginx is running in `app_nginx` Container, which handles requests and makes responses.
2. PHP or PHP-FPM is put in `app_php` Container, it retrieves php scripts from host, interprets, executes then responses to Nginx. If necessary, it will connect to `app_mysql` as well.
3. MySQL lies in `app_mysql` Container, 

Our app scripts are located on host, you can edit files directly without rebuilding/restarting whole images/containers.

### Build and Run

At first, you should have had [Docker](https://docs.docker.com) and [Docker Compose](https://docs.docker.com/compose) installed.

So you can launch:

    $ sudo docker-compose up -d

For more operations to containers, please refer to:

    $ sudo docker-compose --help

After the build check out your `localhost`

### Important

If you are testing on your machine, make sure that ports `80` and `3306` are avaiable

### Pull Requests? 
We love them!

### Comments?
Let's hear them!

### Webeetle? 
In case you're interested we are [Webeetle](http://www.webeetle.com) 

  [1]: webeetle_lnmp_architecture.jpg
