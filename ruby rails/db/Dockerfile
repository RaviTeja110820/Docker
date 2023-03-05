FROM mysql:latest

ENV MYSQL_ROOT_PASSWORD=mysql@123
ENV MYSQL_DATABASE=mydb
ENV MYSQL_USER=myuser
ENV MYSQL_PASSWORD=mypassword

ADD setup.sql /docker-entrypoint-initdb.d

EXPOSE 3306
CMD ["mysqld"]