# Deploy multiple Django websites automatically

This script allows you to install multiple websites on the Django framework. It automatically installs all the necessary dependencies (Nginx, Gunicorn, MariaDB) on the server, prepares a python virtual environment, and configure the MariaDB database. Just by typing one command in the command line, you get the fully working Django website with configured database (MariaDB) and on your own domain.

## Usage

Execute this command on your server:

```curl -o addsite https://raw.githubusercontent.com/jdbit/django-auto-deploy/master/addsite && chmod +x addsite && sudo ./addsite```

Enter the desired website and domain name when requested and your website is ready to use!

All the sites will be placed to /var/www/{SITENAME} directory. Before running the script, make sure there is no folder in /var/www named as the site you are going to create.

The script creates Python virtual environment in /var/www/{SITENAME}/env directory, you can activate the virtual environment by this command:

```
source env/bin/activate
```
and exit from the python virtual environment with this command:
```
deactivate
```

You can set up as many Django websites as you want with this script. 

The script creates a new MySQL database, a new DB user, and adds the necessary DB settings to DATABASES dict in settings.py.

If you need a good and not expensive hosting for your Django projects, [check DigitalOcean](https://m.do.co/c/008d3315ed7b) (get $100 in credit for 60 days through my referral link), you can run a few Django websites on a single virtual server just for 5$/month. I've tested it on the latest Ubuntu Server 20.04 installed on DigitalOcean 5$/month droplet.
