
FROM mysql:5.7 AS db01

# Set required MySQL environment variables While Docker Compose
#ENV MYSQL_ROOT_PASSWORD=admin123
#ENV MYSQL_DATABASE=accounts
#ENV MYSQL_USER=admin
#ENV MYSQL_PASSWORD=

#Expose Ports
EXPOSE 3306

# Copy your SQL dump into MySQL initialization folder
COPY ./init.sql /docker-entrypoint-initdb.d/init.sql