FROM php:7.1.18-apache

RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng-dev \
    gnupg2 \
    git \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

RUN apt-get -y update \
    && apt-get install -y libicu-dev\
    && docker-php-ext-configure intl \
    && docker-php-ext-install intl

RUN docker-php-ext-install pdo_mysql bcmath mbstring

#RUN docker-php-ext-install pdo_mysql

#RUN docker-php-ext-install bcmath

RUN apt-get update \
	&& apt-get install -y \
	libxml2-dev \
	libxslt-dev \
	&& docker-php-ext-install -j$(nproc) \
		dom \
		xmlrpc \
		xsl

RUN apt-get update \
    && apt-get install -y \
        libbz2-dev \
        zlib1g-dev \
        && docker-php-ext-install -j$(nproc) \
            zip \
            bz2

RUN docker-php-ext-install -j$(nproc) \
    soap \
	sockets \
	calendar \
	sysvmsg \
	sysvsem \
	sysvshm

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

#RUN a2enmod rewrite && service apache2 restart

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - && apt-get install -y nodejs && apt-get install -y npm

RUN curl -o- -L https://yarnpkg.com/install.sh | bash
	
RUN a2enmod rewrite

COPY apache_config.conf /etc/apache2/sites-enabled/000-default.conf

COPY php.ini /usr/local/etc/php/php.ini
