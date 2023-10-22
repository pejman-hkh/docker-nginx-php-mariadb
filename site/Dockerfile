From pejmanhkh/alpine

RUN apk update;\
apk add --no-cache certbot nginx php81 php81-common php81-mysqlnd php81-pdo php81-pdo_dblib php81-pdo_odbc php81-pdo_mysql php81-pdo_sqlite php81-mbstring php81-gettext php81-iconv php81-zip php81-curl php81-dom php81-session php81-mysqli php81-gd php81-fpm bash;\
mkdir -p /usr/local/php81/sockets/; \
mkdir -p /usr/local/data/certs;

EXPOSE 80 443 9000

COPY lib/rar.so /usr/lib/php81/modules/rar.so
COPY lib/ctype.so /usr/lib/php81/modules/ctype.so
COPY lib/02_rar.ini /etc/php81/conf.d/02_rar.ini
COPY supervisord.conf /etc/supervisord.conf

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisord.conf"]