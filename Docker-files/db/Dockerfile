FROM mysql:8.0.33
LABEL "Porject"="Vprofile"
LABEL "Author"="Eric"

ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MSQL_DATABASE="accounts"

ADD db_backup.sql docker-entrypoint-initdb/db_backup