FROM tomcat:9-jdk17

# Install Maven and create working directory
RUN apt update -y && apt install maven -y && mkdir /dir1

# Copy source code into container
COPY . /dir1
WORKDIR /dir1

# Build the Java project
RUN mvn package
# Deploy WAR to default Tomcat webapps directory
RUN cp target/webapp-0.1.war /usr/local/tomcat/webapps

# Expose the Tomcat port
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]

