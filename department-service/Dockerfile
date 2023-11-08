FROM maven:3.9-eclipse-temurin-11-alpine AS build
COPY . ./opt/app
WORKDIR /opt/app
RUN mvn clean package

FROM eclipse-temurin:11-jre-alpine
COPY --from=build /opt/app/target/*.jar /opt/app/department-service.jar
ENTRYPOINT ["java","-jar","/opt/app/department-service.jar"]
EXPOSE 9001