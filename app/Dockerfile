# Utilizando a versão oficial com PHP versão 7.4.0 e Apache
FROM php:apache
EXPOSE 80

# Habilitando o modo de reescrita do Apache
RUN a2enmod rewrite

RUN apt-get update
RUN apt-get install -y libpq-dev
RUN apt-get install -y zlib1g-dev libzip-dev libpng-dev
RUN apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libgd-dev

# Instalação de extensões básicas do PHP
# Qualquer nova extensão pode ser adiconada aqui
# OBS Utilizar sempre o docker-php-ext-install quando possível ao invés de apt-get,
# pois ele instala e configura as extensões baixadas
RUN docker-php-ext-configure gd --with-jpeg=/usr/include/ --with-freetype=/usr/include/
RUN docker-php-ext-install gd
RUN docker-php-ext-install zip
RUN docker-php-ext-install mysqli pdo pdo_mysql
