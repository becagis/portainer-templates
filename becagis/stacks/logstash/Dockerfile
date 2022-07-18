ARG LOGSTASH_VERSION=8.3.2
FROM logstash:${LOGSTASH_VERSION}

LABEL maintainer="Truong Thanh Tung <ttungbmt@gmail.com>"

ARG POSTGRES_JDBC_VERSION=42.4.0

RUN logstash-plugin install logstash-integration-jdbc

# Add lib database jdbc jars
RUN curl https://jdbc.postgresql.org/download/postgresql-${POSTGRES_JDBC_VERSION}.jar -o /usr/share/logstash/logstash-core/lib/jars/postgresql-jdbc.jar

# https://www.ibm.com/docs/en/cabi/1.1.2?topic=databases-downloading-database-driver-jar-files
#COPY ./compose/mysql/mysql-connector-java-8.0.11.jar /usr/share/logstash/logstash-core/lib/jars/mysql-connector-java.jar
#COPY ./compose/sql-server/mssql-jdbc-7.4.1.jre11.jar /usr/share/logstash/logstash-core/lib/jars/mssql-jdbc.jar
#COPY ./compose/oracle/ojdbc6-11.2.0.4.jar /usr/share/logstash/logstash-core/lib/jars/ojdbc6.jar
#COPY ./compose/postgres/postgresql-42.2.8.jar /usr/share/logstash/logstash-core/lib/jars/postgresql.jar