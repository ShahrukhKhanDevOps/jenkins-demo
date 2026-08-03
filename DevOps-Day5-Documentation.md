# DevOps Training - Day 5 Documentation

## Environment

- OS : Ubuntu 24.04 LTS
- Jenkins Version : Latest LTS
- Java : OpenJDK 21
- Maven : 3.8.7
- Node.js : v18
- NPM : v9
- .NET SDK : 8.0
- Git : Installed

---

# GitHub Repository

Repository URL

git@github.com:ShahrukhKhanDevOps/jenkins-demo.git

---

# Jenkins Jobs

## 1. Angular-Linux-Freestyle

### Purpose

Build Angular application using npm.

### Build Steps

- Clone Repository
- Navigate to AngularDemo
- npm install
- npm run build

### Output

dist/angular-demo

Status

SUCCESS

---

## 2. Maven-Linux-Freestyle

### Purpose

Build Java Maven Project.

### Build Steps

- Clone Repository
- Navigate to MavenDemo
- mvn clean package

### Output

target/MavenDemo-1.0-SNAPSHOT.jar

Status

SUCCESS

---

# Jenkins Pipelines

---

## Maven Pipeline

Pipeline Name

Maven-Pipeline

Stages

- Checkout
- Build
- Archive

Build Command

mvn clean package

Artifacts

target/*.jar

Status

SUCCESS

---

## Angular Pipeline

Pipeline Name

Angular-Pipeline

Stages

- Checkout
- Install Dependencies
- Build
- Archive

Build Commands

npm install

npm run build

Artifacts

dist/angular-demo/browser/**

Status

SUCCESS

---

## DotNet Pipeline

Pipeline Name

DotNet-Linux-Pipeline

Stages

- Checkout
- Restore
- Build
- Publish
- Archive

Commands

dotnet restore

dotnet build --configuration Release

dotnet publish -c Release -o publish

Artifacts

publish/**

Status

SUCCESS

---

# Jenkins Features Practiced

- Freestyle Jobs
- Pipeline Jobs
- Git Integration
- GitHub SSH Authentication
- Archive Artifacts
- Fingerprint Artifacts
- Workspace Cleanup
- Parameterized Builds
- Maven Build
- Angular Build
- DotNet Build

---

# Issues Faced

## Maven

Issue

Source option 5 is no longer supported.

Resolution

Updated pom.xml to Java 21.

---

Issue

Missing POM

Resolution

Executed Maven inside MavenDemo directory.

---

## Angular

Issue

Node dependencies missing.

Resolution

Executed npm install before build.

---

## DotNet

Issue

Pipeline executed from workspace root.

Resolution

Used

dir('DotNetDemo')

inside Jenkins Pipeline.

---

# Outcome

Successfully created

- Angular Freestyle Job

- Maven Freestyle Job

- Angular Pipeline

- Maven Pipeline

- DotNet Pipeline

All builds completed successfully.
