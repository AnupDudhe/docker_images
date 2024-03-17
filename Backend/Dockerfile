FROM centos:7
LABEL webapp="Studentapp"
LABEL DevopsEngg="Anup"
WORKDIR /opt
RUN yum install java -y 
ADD https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.99/bin/apache-tomcat-8.5.99.tar.gz .
RUN tar -xzvf apache-tomcat-8.5.99.tar.gz
WORKDIR apache-tomcat-8.5.99
COPY student.war   webapps/student.war
ADD  https://s3-us-west-2.amazonaws.com/studentapi-cit/mysql-connector.jar lib/
COPY context.xml conf/context.xml

EXPOSE 8080
CMD bin/catalina.sh start


