FROM openjdk:11
RUN apt-get update && apt-get install -y maven
COPY . /opt/app
WORKDIR /opt/app
RUN mvn clean package
ARG JAR_FILE=target/*.jar
RUN cp ${JAR_FILE} user-service.jar
# COPY ${JAR_FILE} user-service.jar
ENTRYPOINT ["java","-jar","/user-service.jar"]
EXPOSE 9002