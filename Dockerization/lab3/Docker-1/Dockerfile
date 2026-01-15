# Stage 1: build with Maven + Java 17
FROM maven:3.9.0-eclipse-temurin-17 AS build
WORKDIR /app

# copy only pom first to leverage layer caching if dependencies don't change
COPY pom.xml .
# if using a settings or .mvn wrapper adjust accordingly
# copy source code
COPY src ./src

# build the app (runs tests by default)
RUN mvn -B package

# Stage 2: run the jar on a lightweight JDK image
FROM eclipse-temurin:17-jdk-jammy
WORKDIR /app

# Copy the built jar (adjust name if different)
COPY --from=build /app/target/demo-0.0.1-SNAPSHOT.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java","-jar","/app/app.jar"]

