FROM wordpress:php8.2-fpm

# Installing nginx
RUN apt-get update \
    && apt-get install -y nginx \
    && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libmcrypt-dev vim \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Installing PHP Extensions
RUN docker-php-ext-configure gd --with-freetype --with-jpeg && \
    docker-php-ext-install mysqli pdo pdo_mysql gd


COPY . /var/www/html

# Running nginx and php-fpm and clear WP-Rocket cache
CMD ["sh", "-c", "service nginx start && php-fpm"]
