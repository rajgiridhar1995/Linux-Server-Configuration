# Linux Server Configuration

> Raj Giridhar K

## About

This is the final project of Udacity's [Full Stack Web Developer Nanodegree](https://in.udacity.com/course/full-stack-web-developer-nanodegree--nd004/?). In this project, the Item Catalog project will be deployed on a remote linux server running in AWS.

## Server Info

- **Public IP** : 3.85.24.212
- **SSH Port** : 2200
- **Public DNS** : ec2-3-85-24-212.compute-1.amazonaws.com

## Getting Started

This Project uses AWS EC2 instance to run the remote web server. The operating system chosen was Ubuntu 18.04. The free tier configuration was chosen in the instance configuration.

#### Application Installed
- Apache2
- Postgresql
- libapache2-mod-wsgi
- git
- python-pip

And python2 packages like flask, SQLAlchemy, oauth2client, httplib2, psycopg2.

 #### Configurations

 - The SSH default port (22) was changed to 2200. To remotely connect to the instance you need to run the command `ssh grader@3.85.24.212 -i "private-key" -p 2200`.

 - Uncomplicated Firewall (UFW) has been setup in the instance that allows incoming connection from the following ports :
    - SSH (port 2200)
    - HTTP (port 80)
    - NTP (port 123)

    Also, a security group (AWS security group)was configured with the same inbound rules and it was attached to this instance.

- The user `grader` was given sudo access.
- Apache web server was configured to serve the python application on port 80 (default port for http).

- Instead of using sqlite as a database in the flask application, postgresql was used and a new user `catalog` was created in database with password `password`.

## References

1) https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-an-ubuntu-and-debian-cloud-server
2) https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
3) https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-14-04
4) https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-14-04
