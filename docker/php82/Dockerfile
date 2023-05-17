FROM php:8.2-fpm

# Install packages and php extensions, esp. those to use with mysql: pdo, pdo_mysql, mysqli
RUN apt-get update && apt-get install -y \
    libxml2-dev \
    gettext \
    libpng-dev \
    libzip-dev \
    libfreetype6-dev \
    libmcrypt-dev \
    libjpeg-dev \
    libjpeg62-turbo-dev \
  && docker-php-ext-configure gd --with-freetype --with-jpeg \
  && docker-php-ext-install -j$(nproc) gd intl exif gettext iconv zip pdo pdo_mysql mysqli bcmath soap xml opcache

# Use the default production configuration & adjust some options
RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"
RUN sed -i 's/^upload_max_filesize.*$/upload_max_filesize = 2G/g' $PHP_INI_DIR/php.ini
RUN sed -i 's/^post_max_size.*$/post_max_size = 2G/g' $PHP_INI_DIR/php.ini
RUN sed -i 's/^memory_limit.*$/memory_limit = 2G/g' $PHP_INI_DIR/php.ini
RUN sed -i 's/^max_execution_time.*$/max_execution_time = 120/g' $PHP_INI_DIR/php.ini
