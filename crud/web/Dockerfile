FROM debian:stable-slim

RUN apt-get update && apt-get install -q -y apache2 && apt-get autoclean -y

COPY *.php /var/www/html/

RUN apt-get install -q -y php-mysql php && \
  rm -f /var/www/html/index.html && apt-get autoclean -y

EXPOSE 80

WORKDIR /var/www/html

ENTRYPOINT apache2ctl -D FOREGROUND
