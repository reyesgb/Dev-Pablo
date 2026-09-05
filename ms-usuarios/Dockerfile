FROM eclipse-temurin:21-jre

WORKDIR /app

COPY ms-usuarios/target/*.jar app.jar

EXPOSE 9001

ENTRYPOINT ["java", "-jar", "app.jar"]