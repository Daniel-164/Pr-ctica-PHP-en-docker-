FROM debian:bullseye
MAINTAINER Daniel Pérez "dapega01@gmail.com"

RUN apt-get update && apt-get install -y apache2 \
libapache2-mod-php7.4 \
php7.4 \
php7.4-mysql \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/*

EXPOSE 80

RUN rm /var/www/html/index.html
COPY bookmedik /var/www/html/
ADD script.sh /usr/local/bin/

RUN chmod +x /usr/local/bin/script.sh

ENV DATABASE_USER bookmedik
ENV DATABASE_PASSWORD bookmedik
ENV DATABASE_HOST db

CMD ["script.sh"]
