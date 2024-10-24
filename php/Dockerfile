FROM php:7.2-fpm
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libicu-dev \
        libonig-dev \
        libxml2-dev \
        libcurl4-openssl-dev \
        libssl-dev \
        libzip-dev \
        vim \
        wget \
        unzip \
        git
RUN docker-php-ext-install -j$(nproc) zip 
RUN docker-php-ext-install -j$(nproc) iconv 
RUN docker-php-ext-install -j$(nproc) intl
RUN docker-php-ext-install -j$(nproc) xml 
RUN docker-php-ext-install -j$(nproc) soap
#RUN docker-php-ext-install -j$(nproc) json
RUN docker-php-ext-install -j$(nproc) session
#RUN docker-php-ext-install -j$(nproc) tokenizer
RUN docker-php-ext-install -j$(nproc) opcache 
RUN docker-php-ext-install pdo pdo_mysql mysqli mbstring ctype curl fileinfo ftp 
RUN docker-php-ext-configure gd
RUN docker-php-ext-install -j$(nproc) gd 
RUN docker-php-ext-configure calendar && docker-php-ext-install calendar

RUN mkdir /composer-setup && wget https://getcomposer.org/installer -P /composer-setup && php /composer-setup/installer --install-dir=/usr/bin && rm -Rf /composer-setup    
