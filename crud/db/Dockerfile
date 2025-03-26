FROM debian:stable-slim

RUN apt-get update && apt-get install -q -y mariadb-server && apt-get autoclean -y

RUN sed -i "s/.*bind-address.*/bind-address = 0.0.0.0/" /etc/mysql/mariadb.conf.d/50-server.cnf

COPY database.sql /

RUN service mariadb start && mysql < /database.sql

EXPOSE 3306

ENTRYPOINT mysqld_safe
