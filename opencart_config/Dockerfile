FROM php:5.6-apache

RUN docker-php-ext-install mysql mysqli

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    git \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libxpm-dev \
    libvpx-dev \
&& docker-php-ext-configure gd \
    --with-freetype-dir=/usr/lib/x86_64-linux-gnu/ \
    --with-jpeg-dir=/usr/lib/x86_64-linux-gnu/ \
    --with-xpm-dir=/usr/lib/x86_64-linux-gnu/ \
    --with-vpx-dir=/usr/lib/x86_64-linux-gnu/ \
&& docker-php-ext-install gd
RUN a2enmod rewrite
RUN curl -o ioncube.tar.gz http://downloads3.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz \
    && tar -xvvzf ioncube.tar.gz \
    && mv ioncube/ioncube_loader_lin_5.6.so `php-config --extension-dir` \
    && rm -Rf ioncube.tar.gz ioncube \
    && docker-php-ext-enable ioncube_loader_lin_5.6

RUN cd /var/www/


RUN git clone  https://github.com/vstepencko/xcraft_opencart

RUN mv ./xcraft_opencart/* /var/www/html/

COPY ./configs/config.php /var/www/html/config.php

COPY ./configs/config_admin.php /var/www/html/91VitZen85/config.php

WORKDIR /var/www/html
