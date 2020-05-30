# Deploy as much as you want Django websites with one simple command

This script allows you to set up multiple Django websites easily. It automatically installs all the necessary dependencies (Nginx, Gunicorn, MySQL, Django MySQL connector) on your Ubuntu server, prepares a python virtual environment, and configure the MySQL database. Just by typing one command in the command line, you get the fully working Django website with a configured database (MySQL).

## Features and what is this script doing

1. Generate SFTP/MySQL passwords
2. Create a working directory in `/var/www/`
3. Create a new Linux user and add it to the sftp group
4. Assign user permissions to the working directory
5. Install necessary dependencies: nginx, python3-pip, mysql-server, virtualenv, gunicorn, django, mysql-connector-python
6. Create a new Django project, dabase, and configure Django to work with the MySQL database
7. Create NGINX and Gunicorn config files (a separate config file for each site)
8. Save passwords to `pass.txt` and create `.gitignore` file

## Usage

Execute this command on your server:

```
curl -o addsite https://raw.githubusercontent.com/jdbit/django-auto-deploy/master/addsite && chmod +x addsite && sudo ./addsite
```

This command will clone the script to the current directory, make it executable, and execute with root privileges.

You just need to enter the desired website and domain name when requested and your website is ready to use!  If you want to add another website, just run the `sudo ./addsite` again.

All the sites will be placed to `/var/www/{SITENAME}` directory. Before running the script, make sure there is no folder in `/var/www` named as the site you are going to create.

In the working directory `/var/www/$SITENAME` two files will be created:
`deploy.log` - all the bash script output will be saved to this file, you can check it to ensure there were no errors during the installation process
`pass.txt` - a file with SFTP and MySQL passwords.

The script creates Python virtual environment in `/var/www/{SITENAME}/env` directory, you can activate the virtual environment by this command:

```
source env/bin/activate
```
and exit from the python virtual environment with this command:
```
deactivate
```


You can set up as many Django websites as you want with this script. 

The script creates a new MySQL database, a new DB user, and adds the necessary DB settings to DATABASES dict in settings.py.


## Warning

Use the script on your own risk. It was tested only with fresh Ubuntu 20.04 Server installation. If you run it on your already configured server, there might be conflicts with other software installed.

## Django hosting recommendation

If you need a good and affordable hosting for your Django projects, [I would recommend DigitalOcean](https://m.do.co/c/008d3315ed7b) (get $100 in credit for 60 days through my referral link), you can run a few simple Django websites on a single virtual server just for 5$/month. I've tested it on the latest Ubuntu Server 20.04 installed on DigitalOcean 5$/month droplet.
