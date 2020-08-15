# Symfony Docker Compose
Docker compose environment for Symfony (works for Laravel also) projects

# Summary of what is included
* PHP 7.4.8 with XDEBUG 2.9.6
* Apache2
* MySQL 5.7
* PhpMyAdmin - manage MySQL
* Mailhog - local mailing server to test emails
* Installs `composer` and `symfony` commands
* Virtualhost configuration dedicated for Symfony projects

# How to install this in my project?

* Download `.docker` folder and `docker-compose.yml` file and add them to your project
* Run `docker-compose up` command from your terminal. [(Install docker compose)](https://docs.docker.com/compose/install/)

# How to access everything?

By default you can access services via:
* Access your project website via - http://192.168.2.2/
* MySQL can be accessed via 192.168.2.3:3306
* PhpMyAdmin can be accessed via http://192.168.2.4/
* Mailhog can be accessed via http://192.168.2.5:8025/
* Access docker apache-php terminal by writing - `docker exec -it project_web bash`

# Modifying .env file

If you use default IP addresses, append your `.env` file with the following:

* For database connection -`DATABASE_URL=mysql://root:@192.168.2.3:3306/project`
* For mailing server - `MAILER_URL=mailhog:1025//randomemail@gmail.com:randompassword` (You don't need to change email or password)

# MySQL

* If you haven't modified IP addresses, you can connect to your MySQL via 192.168.2.3:3306
* If you don't have any additional software, you can connect to database via phpmyadmin (http://192.168.2.4/)
* Nickname: `root`
* There is no password, leave blank for that
* Default table is called `project`

# Notes

* You cannot use same configuration for multiple projects. Docker won't allow you to allocate same IP addresses for multiple containers.
* You would need to modify `docker-compose.yml` IP addresses. For example from `192.168.2.0/24` to `192.168.3.0/24`

# Something does not work?

[Please create an issue.](https://github.com/kasteckis/symfony-docker-compose/issues/new)