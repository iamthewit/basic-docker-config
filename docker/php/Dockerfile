FROM php:7.2-fpm

RUN apt-get update && apt-get install -y \
    libpng-dev \
    libgmp-dev \
    libldap2-dev \
    libpq-dev \
    libxml2-dev \
    libxslt-dev \
    libzip-dev \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install -j$(nproc) gmp \
    && docker-php-ext-configure ldap --with-libdir=lib/x86_64-linux-gnu/ \
    && docker-php-ext-install -j$(nproc) ldap \
    && docker-php-ext-configure opcache --enable-opcache \
    && docker-php-ext-install -j$(nproc) opcache \
    && docker-php-ext-install -j$(nproc) pgsql pdo pdo_pgsql \
    && docker-php-ext-install -j$(nproc) soap \
    && docker-php-ext-install -j$(nproc) xsl \
    && docker-php-ext-configure zip --with-libzip \
    && docker-php-ext-install -j$(nproc) zip



#RUN pecl install xdebug-2.6.0 && docker-php-ext-enable xdebug \
#    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" >> /usr/local/etc/php/php.ini  \
#    && echo "xdebug.remote_autostart = 1" >> /usr/local/etc/php/php.ini  \
#    && echo "xdebug.remote_enable = 1" >> /usr/local/etc/php/php.ini  \
#    && echo "xdebug.remote_handler = dbgp" >> /usr/local/etc/php/php.ini  \
#    && echo "xdebug.remote_mode = req" >> /usr/local/etc/php/php.ini  \
#    && echo "xdebug.remote_port = 9000" >> /usr/local/etc/php/php.ini  \

    # not sure what this does?..
#    && echo "xdebug.remote_connect_back=0" >> /usr/local/etc/php/php.ini \
    # this should be the hosts ip

#    && echo "xdebug.remote_host = 127.0.0.1" >> /usr/local/etc/php/php.ini  \
#    && echo "xdebug.idekey=IDEA_DEBUG" >> /usr/local/etc/php/php.ini \
#    && echo "xdebug.profiler_output_name = xdebug.out.%t" >> /usr/local/etc/php/php.ini  \
#    && echo "xdebug.profiler_output_dir = /tmp" >> /usr/local/etc/php/php.ini  \
#    && echo "xdebug.profiler_enable_trigger = 1" >> /usr/local/etc/php/php.ini

    # jose needs this for the kcachegrind reports
#    \ && echo "xdebug.profiler_enable = 1" >> /usr/local/etc/php/php.ini


# pretty sure we don't need these:
#    php7.2-common \
#    php7.2-cli \
#    php7.2-mysql \