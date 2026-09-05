FROM eclipse-temurin:21-jre

WORKDIR /app

COPY eureka/target/*.jar app.jar

EXPOSE 8761

ENTRYPOINT ["java", "-jar", "app.jar"]