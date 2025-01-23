ARG APACHE_VERSION=""
FROM httpd:${APACHE_VERSION:+${APACHE_VERSION}-}alpine

RUN apk update; \
    apk upgrade;

# Copy apache vhost file to proxy php requests to php-fpm container
COPY demo.apache.conf /usr/local/apache2/conf/demo.apache.conf
RUN echo "Include /usr/local/apache2/conf/demo.apache.conf" \
    >> /usr/local/apache2/conf/httpd.conf

#RUN cp /etc/apache2/mods-available/rewrite.load /usr/local/apache2/mods-enabled/ && \
#    cp /etc/apache2/mods-available/headers.load /usr/local/apache2/mods-enabled/