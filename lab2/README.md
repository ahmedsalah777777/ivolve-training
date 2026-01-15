# Lab 2 – Building and Packaging a Java Application with Maven

## 📌 Overview

This lab demonstrates how to build, test, and package a Java application using **Apache Maven** as a build automation and dependency management tool.  
The objective is to gain hands-on experience with Maven project structure, dependency management, unit testing, and artifact generation.

---

## 🎯 Lab Objectives

- Install and configure Apache Maven
- Clone source code https://github.com/Ibrahim-Adel15/build2.git
- Build a Java application using Maven
- Execute unit tests
- Generate a packaged JAR artifact
- Run and verify the application

---

## 🚀 Step-by-Step Implementation

### 1. Installing Maven ⚙️

#### 1.1 Install Maven
```bash
sudo apt update
sudo apt install -y maven
```
#### 1.2 Verify Maven Installation
```bash
mvn -v
```
![Verify Maven Installation](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab2/lab2_screenshots/Screenshot%20from%202026-01-13%2013-36-59.png)

### 2. Clone the Application Repository 📥
```bash
git clone https://github.com/Ibrahim-Adel15/build2.git
cd build2/
```
![Cloning  App Repository](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab2/lab2_screenshots/Screenshot%20from%202026-01-13%2013-29-53.png)

### 3. Run Unit Tests 🧪
```bash
mvn test
```
![Running Unit Tests](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab2/lab2_screenshots/Screenshot%20from%202026-01-13%2013-31-40.png)

### 4. Build the Application 🏗️
```bash
mvn package
```
![Building the Application](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab2/lab2_screenshots/Screenshot%20from%202026-01-13%2013-32-23.png)

### 5. Run the Application ▶️
```bash
java -jar target/hello-ivolve-1.0-SNAPSHOT.jar
```
![Running the Application](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab2/lab2_screenshots/Screenshot%20from%202026-01-13%2013-32-51.png)
