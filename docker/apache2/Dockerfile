FROM php:7.4-apache

RUN apt-get update && apt-get install -y libssl-dev libxml2-dev libzip-dev zlib1g-dev libonig-dev libpng-dev libjpeg-dev libfreetype6-dev

RUN docker-php-ext-install mbstring xml

RUN docker-php-ext-configure gd --with-freetype --with-jpeg

RUN docker-php-ext-install gd

RUN docker-php-ext-install pdo_mysql json tokenizer && docker-php-ext-enable pdo_mysql gd mbstring xml && a2enmod rewrite

RUN rm -rf /var/lib/apt/lists/*

RUN sed -i '/<Directory \/var\/www\/>/,/<\/Directory>/ s/AllowOverride None/AllowOverride All/' /etc/apache2/apache2.conf
RUN sed -i '/DirectoryIndex, index.cgi/ s/index.html/index.php/' /etc/apache2/mods-enabled/dir.conf
RUN sed -i '/index.pl, index.xhtml/ s/index.php/index.html/' /etc/apache2/mods-enabled/dir.conf
RUN sed -i 's/DocumentRoot \/var\/www\/html/DocumentRoot \/var\/www\/html\/public/' /etc/apache2/sites-enabled/000-default.conf