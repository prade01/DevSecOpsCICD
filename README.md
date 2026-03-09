########################################################################
## DevSecOps CI/CD Pipeline for Java Maven Application

## Project Overview

- This project demonstrates a complete DevSecOps CI/CD pipeline for a Java Maven-based web application using Jenkins. The pipeline automates the entire software delivery process including build, testing, security scanning, artifact management, deployment, and notifications.

- The application is built using Maven, analyzed with SonarQube, scanned for vulnerabilities using Trivy, stored in Nexus Repository, and deployed on Apache Tomcat.

- The pipeline ensures code quality, security compliance, and automated deployment.

## Architechture Diagram

                    +----------------------+
                    |     Developer        |
                    |  Push Code to Git    |
                    +----------+-----------+
                               |
                               v
                       +---------------+
                       |  GitHub Repo  |
                       +-------+-------+
                               |
                               v
                       +---------------+
                       |    Jenkins    |
                       |   Pipeline    |
                       +-------+-------+
                               |
      -------------------------------------------------------
      |        |           |          |          |          |
      v        v           v          v          v          v

  Maven    Checkstyle    JUnit     JaCoCo    SonarQube    Trivy
 Compile   Code Style     Tests   Coverage   Code Scan   Security Scan

      -------------------------------------------------------
                               |
                               v

                      Build WAR Artifact
                               |
                               v

                       +---------------+
                       |     Nexus     |
                       | Artifact Repo |
                       +-------+-------+
                               |
                               v

                       +---------------+
                       |   Apache      |
                       |   Tomcat      |
                       | Deployment    |
                       +-------+-------+
                               |
                               v

                        Slack Notification








## #############################################
Developer
   |
   v
Git/Github Repository
   |
   v
Jenkins Pipeline
   |
   |---- Maven Compile
   |---- Checkstyle
   |---- Unit Tests (JUnit)
   |---- JaCoCo Coverage
   |---- SonarQube Scan
   |---- Trivy Security Scan
   |---- Build Artifact (WAR)
   |
   v
Nexus Repository
   |
   v
Apache Tomcat Deployment
   |
   v
Slack Notification



##

## Tools & Technologies Used
Tool	           Purpose
Jenkins	           CI/CD Automation
Maven	           Build Management
SonarQube	       Code Quality Analysis
Trivy	           Security Vulnerability Scan
Nexus	           Artifact Repository
Apache Tomcat	   Application Deployment
Slack	           Build Notifications
JUnit	           Unit Testing
JaCoCo	           Code Coverage
Checkstyle	       Code Quality Standards

## Jenkins Pipeline Flow
Stage 1  -> Git Clone
Stage 2  -> Maven Compile
Stage 3  -> Checkstyle
Stage 4  -> Unit Tests
Stage 5  -> JaCoCo Coverage
Stage 6  -> SonarQube Scan
Stage 7  -> Trivy Scan
Stage 8  -> Build Artifact
Stage 9  -> Upload to Nexus
Stage 10 -> Deploy to Tomcat
Stage 11 -> Slack Notification


## Prerequisites

Before running the pipeline ensure the following tools are installed:

- Java JDK 17

- Maven 3.9

- Jenkins

- SonarQube JDK 11

- Nexus Repository

- Trivy

- Apache Tomcat

- Slack Webhook


##

## Jenkins Configuration

## Required Jenkins tools:

- JDK 17
- Maven 3.9
- Sonar Scanner


## Required Jenkins plugins:

- Pipeline

- Maven Integration

- SonarQube Scanner

- Slack Notification

- Build Timestamp

- Git Plugin



## Environment Variables (Jenkins)

## Example pipeline environment variables:

- SONAR_HOST_URL
- SONAR_TOKEN
- NEXUS_USERNAME
- NEXUS_PASSWORD
- SLACK_WEBHOOK


## How to Run the Pipeline

- Push the project to Git repository.

- Create a Jenkins Pipeline Job.

- Configure the Git repository URL.

- Select Pipeline Script from SCM.

- Ensure the Jenkinsfile is present in the repository.

- Run Build Now.

- Jenkins will automatically execute all pipeline stages.





## Security Implementation (DevSecOps)

- Security is integrated at multiple levels:

## Security Layer	                 Tool
Static Code Analysis	             SonarQube
Dependency Vulnerability Scan	     Trivy
Secure Artifact Storage	             Nexus
Controlled Deployment	             Jenkins



## Benefits of this Pipeline

- Fully automated CI/CD

- Improved code quality

- Early vulnerability detection

- Automated deployment

- Faster delivery cycle

- Centralized artifact management



## ################################################
Author
Pradeep Sharma
DevOps / Cloud Engineer 