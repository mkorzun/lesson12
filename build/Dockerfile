FROM openjdk:8-jdk
RUN apt update  && apt -y install maven git
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git  /tmp/App42PaaS-Java-MySQL-Sample
RUN mkdir /apps /apps/root /apps/webapps
ADD Config.properties /tmp/App42PaaS-Java-MySQL-Sample/WebContent/Config.properties
RUN cat /tmp/App42PaaS-Java-MySQL-Sample/WebContent/Config.properties
RUN mvn -f /tmp/App42PaaS-Java-MySQL-Sample/pom.xml package && \
        cp -r /tmp/App42PaaS-Java-MySQL-Sample/WebContent/* /apps/root && \
        cp /tmp/App42PaaS-Java-MySQL-Sample/target/*.war /apps/webapps