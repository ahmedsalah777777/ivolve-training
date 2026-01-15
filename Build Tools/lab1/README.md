# Lab 1 – Building and Packaging a Java Application with Gradle

## 📌 Overview

This lab demonstrates how to build, test, and package a Java application using **Gradle** as a build automation tool.  
The objective is to gain hands-on experience with Gradle project structure, dependency management, unit testing, and artifact generation.

---

## 🎯 Lab Objectives

- Install and configure Gradle
- Clone source code https://github.com/Ibrahim-Adel15/build1.git
- Build a Java application using Gradle
- Execute unit tests
- Generate a packaged JAR artifact
- Run and verify the application

---

## 🛠️ Prerequisites

- Linux environment
- Java JDK 17 installed
- Gradle installed
- Git installed

---

## 🚀 Step-by-Step Implementation

### 1. Installing Gradle

#### 1.1 Download and Install Gradle
```bash
sudo apt install -y gradle
```
#### 1.2 Verify Gradle Installation
```bash
gradle -v
```
![Verify Gradle Installation](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab1/lab1_screenshots/Screenshot%20from%202026-01-13%2013-24-30.png)

### 2. Clone the Application Repository
```bash
git clone https://github.com/Ibrahim-Adel15/build1.git
cd build1/
```
![Clonin App Repository](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab1/lab1_screenshots/Screenshot%20from%202026-01-13%2013-25-52.png)
### 3. Run Unit Tests
```bash
gradle clean test
```
![Running Unit Tests](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab1/lab1_screenshots/Screenshot%20from%202026-01-13%2013-27-51.png)

### 4. Build the Application
```bash
gradle build
```
![Building the Application](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab1/lab1_screenshots/Screenshot%20from%202026-01-13%2013-28-31.png)

### 5. Run the Application
```bash
java -jar ./build/libs/ivolve-app.jar
```
![Running the Application](https://github.com/ahmedsalah777777/ivolve-training/blob/main/lab1/lab1_screenshots/Screenshot%20from%202026-01-13%2013-29-13.png)
