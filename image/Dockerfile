FROM debian:jessie-slim

RUN echo "Europe/Rome" > /etc/timezone && dpkg-reconfigure -f noninteractive tzdata

RUN apt-get update --fix-missing -y

RUN apt-get install apache2 wget -y

RUN apt-get install apt-transport-https lsb-release ca-certificates -y
RUN wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list

RUN apt-get update -y
RUN apt-get install php7.2 -y
RUN apt-get install -y php7.2-curl
RUN apt-get install -y php7.2-cli
RUN apt-get install -y php7.2-mysql
RUN apt-get install -y php7.2-xml
RUN apt-get install -y php7.2-soap
RUN apt-get install -y php7.2-gd
RUN apt-get install -y php7.2-mbstring
RUN apt-get install -y php7.2-zip
RUN apt-get install -y php7.2-intl
RUN apt-get install -y php7.2-opcache
RUN apt-get install -y php7.2-tidy
RUN apt-get install -y php-pear
RUN apt-get install -y php7.2-dev
RUN apt-get install -y php-memcached
RUN apt-get install -y php-mongodb
RUN apt-get install -y nano
RUN apt-get install -y cron
RUN apt-get install -y curl
RUN apt-get install -y sudo
RUN apt-get install -y git

RUN pecl install mongodb

RUN apt-get -y install gcc make g++ autoconf libc-dev pkg-config
RUN apt-get -y install libmcrypt-dev
RUN pecl install mcrypt-1.0.1
RUN bash -c "echo extension=/usr/lib/php/20170718/mcrypt.so > /etc/php/7.2/cli/conf.d/mcrypt.ini"
RUN bash -c "echo extension=/usr/lib/php/20170718/mcrypt.so > /etc/php/7.2/apache2/conf.d/mcrypt.ini"

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/bin/composer

RUN a2enmod php7.2
RUN a2enmod rewrite
RUN a2enmod headers
RUN a2enmod ssl

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid

EXPOSE 80
WORKDIR /var/www/html/

CMD /usr/sbin/apache2ctl -D FOREGROUND
