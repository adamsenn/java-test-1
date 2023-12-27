FROM gradle:7-jdk17-alpine AS builder
COPY . .
RUN gradle build

FROM openjdk:17-jdk-alpine
WORKDIR /opt/app
COPY --from=builder /home/gradle/build/libs/*.jar app.jar
ENTRYPOINT ["java","-jar","app.jar"]
EXPOSE 8080