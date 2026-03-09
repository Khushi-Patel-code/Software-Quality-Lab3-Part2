# SOFE3980U – Lab 3 Part 2  
## Continuous Integration and Continuous Delivery using Jenkins

### Repository
https://github.com/Khushi-Patel-code/Software-Quality-Lab3-Part2

### Videos
[Video1: CI Part (two techniques)](https://drive.google.com/file/d/1Hd7_cvI3WwhQyRMy4GVhMzJ-RfD4_ROV/view?usp=sharing)
Video2: Design Part

# Discussion

## Pipeline
A pipeline in Jenkins is a sequence of automated steps that define the process of building, testing, and deploying an application. Pipelines are usually defined in a `Jenkinsfile`, which allows the workflow to be written as code.

## Node
A node is a machine where Jenkins runs jobs. It provides the environment and resources needed to execute builds and pipeline tasks.

## Agent
An agent is a worker that runs tasks from a Jenkins pipeline. It executes stages and steps on a node. In this lab, Kubernetes pods were used as Jenkins agents.

## Stage
A stage represents a major step in the pipeline. Each stage groups related tasks together, such as testing, building, or deploying the application.

## Steps
Steps are the individual commands inside a stage that Jenkins executes. Examples include running tests, building the project with Maven, or executing deployment commands.

# Design

The Binary Calculator project was integrated with Jenkins to implement Continuous Integration and Continuous Deployment (CI/CD).

The Jenkins pipeline is defined in `BinaryCalculatorWebapp/Jenkinsfile_v2`. The pipeline runs automatically when changes are pushed to the GitHub repository.

The pipeline includes the following stages:

1. **Test** – Runs the test cases for the Binary Calculator project.
2. **Build** – Builds the project using Maven.
3. **Containerize** – Builds a Docker image and pushes it to the Artifact Registry.
4. **Deployment** – Deploys the application to the Google Kubernetes Engine (GKE) cluster.
5. **Service** – Creates a load balancer service and exposes the application with an external IP address.

After the pipeline finishes successfully, Jenkins displays the external IP address of the deployed application in the console output.

To access the Binary Calculator application:

1. Open **Jenkins Dashboard**
2. Open the job **BinaryCalculator_cicd**
3. Click the **most recent completed build**
4. Click **Console Output**
5. Scroll to the bottom to find the external IP address
6. Open the following URL in a browser

```
http://<external-ip>:8080
```
