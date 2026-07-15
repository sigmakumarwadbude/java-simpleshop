FROM eclipse-temurin:21-jdk

WORKDIR /app

COPY .mvn/ .mvn/
COPY mvnw mvnw.cmd pom.xml ./

RUN chmod +x mvnw && ./mvnw dependency:go-offline -B

EXPOSE 8080

CMD ["./mvnw", "spring-boot:run"]