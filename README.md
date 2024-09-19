# Deployment of  Java Spring Boot Application to AWS Elastic Beanstalk Using GitHub Actions

### Objective: A guide to walk  through deployment of  a Java Spring Boot application (built with Java 17) to AWS Elastic Beanstalk using GitHub Actions.

## Prerequisites
The following prerequisites were put in place:

1. Java Spring Boot Application: A Spring Boot application built with Java 17.
2. AWS Elastic Beanstalk Environment: An Elastic Beanstalk environment created in your AWS account.
3. AWS Credentials: Access keys (AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY) with the required permissions to deploy to Elastic Beanstalk.
4. GitHub Repository: A GitHub repository containing Java application.
5. VS code: Installed and configured on the local machine.

## Step 1: Create an AWS Elastic Beanstalk Application and Environment

Log in to your AWS Console.
1. Navigate to Elastic Beanstalk.
2. Create a new application with the appropriate settings.
3. Create an environment (Java 17 platform).
4. Ensure you have your Elastic Beanstalk Application Name and Environment Name. e.g
   a.  Application name: mt-java-application
   b.  Environment name: Mt-java-application-env

## Step 2: Set Up AWS Credentials in GitHub

Go to your GitHub repository.
Navigate to Settings > Secrets and variables > Actions.
Click New repository secret.
Add the following secrets:
1. AWS_ACCESS_KEY_ID: Your AWS Access Key.
2. AWS_SECRET_ACCESS_KEY: Your AWS Secret Key.

## Step 3: Create a GitHub Actions Workflow
Create a GitHub Actions workflow to automate the build and deployment process.

Inside project directory, create the directory .github/workflows/.
Create a new YAML file inside the .github/workflows/ directory (e.g., mt-project.yml)

![Screenshot 2024-09-19 054819](https://github.com/user-attachments/assets/c5f41511-fa5d-468d-97cd-b443abf9f973)
![Screenshot 2024-09-19 054929](https://github.com/user-attachments/assets/1c02699f-431b-48b3-bc1b-788eb9715729)

Breakdown of the Workflow:
1. Checkout code: This step checks out your code from the repository.
2. Set up JDK 17: This configures the Java 17 runtime.
3. Cache Maven packages: Speeds up the build process by caching dependencies.
4. Build with Maven: Builds your Java Spring Boot application using Maven.
5. Deploy to Elastic Beanstalk: This uploads the application to S3 and deploys it to your Elastic Beanstalk environment

Step 4: Commit and Push
Commit and push the changes to your GitHub repository:

1. git add .
2. git commit -m "Add GitHub Actions for Elastic Beanstalk deployment"
3. git push origin main

## Step 5: Verify Deployment

Once the commit and push is successfully, navigate to your Github dashboard.


Verify that the new version of your application is running in your environment.
Access your application via the provided URL.






