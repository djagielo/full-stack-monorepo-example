FROM maven:3-jdk-11 as build
WORKDIR '/app'
ADD pom.xml /app/
RUN mvn -B dependency:resolve-plugins dependency:resolve
COPY . .
RUN mvn clean package

FROM openjdk:11-jdk
WORKDIR '/app'
EXPOSE 8080
COPY --from=build /app/target/backend-0.0.1-SNAPSHOT.jar /app
CMD ["java", "-jar", "backend-0.0.1-SNAPSHOT.jar"]