FROM tomcat:9-jdk17
RUN apt update -y && apt install maven -y && mkdir /dir1
COPY . /dir1
WORKDIR /dir1
RUN mvn package && \
    cp /dir1/target/surya-latest.war /usr/local/tomcat/webapps/ && \
    chmod 777 /usr/local/tomcat/webapps/surya-latest.war
EXPOSE 8080
CMD ["catalina.sh", "run"]

