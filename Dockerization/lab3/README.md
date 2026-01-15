# Lab 3 – Containerizing a Java Spring Boot Application with Docker 🐳

## 📌 Overview

This lab demonstrates how to containerize a **Java Spring Boot application** using **Docker**.  
The objective is to gain hands-on experience with writing Dockerfiles, building Docker images, running containers, and verifying application functionality inside a containerized environment.

---

## 🎯 Lab Objectives

- Install and configure Docker
- Clone the Spring Boot application source code
- Write a Dockerfile for the application
- Build a Docker image
- Run a Docker container
- Verify the application is accessible

---

## 🚀 Step-by-Step Implementation

### 1. Installing Docker

```bash
sudo apt update
sudo apt install -y docker.io
```
### 2. Clone the Spring Boot application source code
```bash
git clone https://github.com/Ibrahim-Adel15/Docker-1.git
cd Docker-1
```

![Clone Spring Boot App](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab3/lab3_screenshots/Screenshot%20from%202026-01-13%2014-49-04.png)

### 3. Write a Dockerfile for the application
```bash
vim Dockerfile
```
```dockerfile
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

```
### 3. Build the Docker Image

```bash
docker build -t app1:1.0 .
```

![Build Docker Image](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab3/lab3_screenshots/Screenshot%20from%202026-01-13%2014-50-20.png)

### 4. Run the Container

```bash
docker run -d --name container1 -p 8080:8080 app1:1.0
docker ps
```
![Run Docker Container](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab3/lab3_screenshots/Screenshot%20from%202026-01-13%2014-47-34.png)

### 5. Verify the application is accessible
```bash
curl -v http://localhost:8080/
```
![Verify the application](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab3/lab3_screenshots/Screenshot%20from%202026-01-13%2014-46-26.png)

### 6. Stop and delete the container
```bash
docker stop container1
docker rm container1
```



