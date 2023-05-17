FROM httpd:2.4.29

COPY churchcrm.apache.conf /usr/local/apache2/conf/churchcrm.apache.conf

RUN echo "Include /usr/local/apache2/conf/churchcrm.apache.conf" \
>> /usr/local/apache2/conf/httpd.conf

# Change owner:group of apache files away from root
RUN chown -hR www-data:www-data /usr/local/apache2

# Set permissions -rw-r--r-- (user: read+write, group: read only, others: read only) on htdocs files
RUN find /usr/local/apache2/htdocs -type f -exec chmod 644 '{}' \;
# Set permissions drwxr-xr-x (user: read+write+execute, group: read+execute, others: read+execute) on htdocs directories
RUN find /usr/local/apache2/htdocs -type d -exec chmod 755 '{}' \;

USER www-data