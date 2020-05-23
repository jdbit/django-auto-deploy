# Deploy multiple Django websites automatically

This script allows you to install multiple websites on the Django framework. It automatically installs all the necessary dependencies (Nginx, Gunicorn, MariaDB) on the server, prepares a python virtual environment, and configure the MariaDB database. Just by typing one command in the command line, you get the fully working Django website on your own domain.

## Usage:

Execute this command on your server:

`curl -o addsite https://raw.githubusercontent.com/jdbit/django-auto-deploy/master/addsite && chmod +x addsite && sudo ./addsite`

Enter the desired website and domain name when requested and your website is ready to use!
You can set up as many Django as you want with this script. I've tested it on the latest Ubuntu Server 20.04 installed on DigitalOcean droplet. 
