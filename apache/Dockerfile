FROM httpd:2.4.33-alpine
RUN apk update; \
    apk upgrade;
# Copy apache config file
COPY apache.conf /usr/local/apache2/conf/apache.conf
RUN echo "Include /usr/local/apache2/conf/apache.conf" \
    >> /usr/local/apache2/conf/httpd.conf