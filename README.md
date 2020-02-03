**INTRO**
--
This is a basic [Docker Compose](https://docs.docker.com/compose/) configuration file for application with php, nginx and mysql services enabled.

I created this project, because I was going through online courses in [Udemy](https://www.udemy.com/) and instead of using the offered XAMPP stack I wanted to learn and improve my Docker skills.

It uses the default [nginx](https://hub.docker.com/_/nginx/) and [mysql](https://hub.docker.com/_/mysql/) images from Docker Hub and a bit modified [php](https://hub.docker.com/_/php/) image to be able to talk with mysql service.

**HOW TO**
--
I ran this on MacOS High Sierra 10.13.6, with Docker version 2.1.0.5.

1. install and start [Docker](https://www.docker.com/products/docker-desktop)
2. Clone or download the contents of this repository
3. Open terminal and go to directory containing the **docker-compose.yml**
4. Run `docker-compose up`

**N.B.** On the first run it will download all the necessary Docker images and because we have a bit modified php image, it will install the _pdo_mysql_ extension. If everything goes right, container for each of the service will be created.

5. In browser, open http://localhost:8080 . You should see the output of `phpinfo()`
6. Run `docker-compose down` to stop (and remove) the containers

**NOTES**
--
For nginx to be able to communicate with fpm, I have created a basic nginx config file - **site.conf**. Note that fastcgi_pass parameter references the php service name from compose file.

```
fastcgi_pass php:9000;
``` 



