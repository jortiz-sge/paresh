FROM paresh/java:7

ENV TOMCAT_MAJOR 7
ENV TOMCAT_VERSION 7.0.57

RUN opkg-install curl

RUN curl -kLO https://archive.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz &&\
    gunzip apache-tomcat-${TOMCAT_VERSION}.tar.gz &&\
    tar -xf apache-tomcat-${TOMCAT_VERSION}.tar -C /opt &&\
    rm apache-tomcat-${TOMCAT_VERSION}.tar &&\
    ln -s /opt/apache-tomcat-${TOMCAT_VERSION} /opt/tomcat &&\
    rm -rf /opt/tomcat/webapps/examples /opt/tomcat/webapps/docs /opt/tomcat/bin/*.bat

ENV CATALINA_HOME /opt/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
WORKDIR $CATALINA_HOME

EXPOSE 8080
CMD ["catalina.sh", "run"]
