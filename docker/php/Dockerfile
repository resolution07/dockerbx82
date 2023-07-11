FROM php:8.2-fpm

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    pkg-config \
    libpng-dev \
    libjpeg62-turbo-dev \
    libxpm-dev \
    libwebp-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    libyaml-dev \
    unzip \
    libzip-dev \
    libldap2-dev \
    libfreetype6-dev \
# Clear cache
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Configure PHP extensions
RUN docker-php-ext-configure gd --enable-gd \
     --with-freetype \
     --with-jpeg \
     --with-webp \
# Install PHP extensions
      && docker-php-ext-install mysqli \
    opcache \
    mbstring \
    exif \
    pcntl \
    gd \
    bcmath \
    soap \
    zip \
    intl \
    #&& export ORACLE_HOME=instantclient,/opt/oracle/instantclient_12_1 \
    && pecl install redis xdebug yaml && docker-php-ext-enable redis xdebug yaml

# Get latest Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY php.ini /usr/local/etc/php/php.ini

RUN usermod -u 1000 www-data \
    && chmod 777 -R /tmp \
    && chmod o+t -R /tmp \
    && chmod 777 -R /var/www \
    && chmod o+t -R /var/www

USER www-data

WORKDIR /var/www/bitrix
