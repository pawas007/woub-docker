FROM node:16

WORKDIR /var/www

# Install dependencies
RUN apt-get update && apt-get install -y \
    locales \
    zip \
    vim \
    unzip \
    curl \
    sudo \
    npm \
    supervisor


# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

RUN npm install -g laravel-echo-server

COPY . /var/www


ADD  /docker/node/supervisord.conf /etc/supervisor/conf.d/supervisord.conf
CMD ["/usr/bin/supervisord"]



