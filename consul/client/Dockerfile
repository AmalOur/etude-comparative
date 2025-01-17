FROM maven:3.4.8-openjdk-17 AS builder
WORKDIR /app
COPY ./src /src
COPY ./pom.xml .
RUN mvn clean package

FROM openjdk:17-jdk-alpine
VOLUME /tmp
ARG JAR_FILE=/app/target/*.jar
COPY --from=builder ${JAR_FILE} client-service.jar
ENTRYPOINT ["java","-jar","/client-service.jar"]