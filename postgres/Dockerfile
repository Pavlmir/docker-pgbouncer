FROM postgres:13

ARG POSTGRESQL_SCHEMA
ARG POSTGRESQL_USER
RUN echo "CREATE SCHEMA IF NOT EXISTS ${POSTGRESQL_SCHEMA} AUTHORIZATION ${POSTGRESQL_USER}; \
          ALTER USER ${POSTGRESQL_USER} SET search_path TO ${POSTGRESQL_SCHEMA}, public;" \
          > /docker-entrypoint-initdb.d/setup.sql

RUN chmod a+r /docker-entrypoint-initdb.d/*