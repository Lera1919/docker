FROM postgres:12

RUN apt update && apt install -y --fix-missing
#    apt-utils \
#    gnupg2 \
#    wget
#RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add - \
#&& echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" | tee  /etc/apt/sources.list.d/pgdg.list

#RUN apt install -y postgis postgresql-12-postgis-2.5

#RUN echo 'CREATE EXTENSION IF NOT EXISTS postgis;' > /docker-entrypoint-initdb.d/init.sql