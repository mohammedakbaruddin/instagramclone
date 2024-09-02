# Web Application CI/CD Project

This project is a basic web application consisting of a login page, registration page, homepage, and profile page with a CI/CD pipeline for automated deployment on AWS. The application is inspired by Instagram and features basic navigation, user authentication, and profile management.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Setup and Deployment](#setup-and-deployment)
- [CI/CD Pipeline](#ci/cd-pipeline)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
This project demonstrates a simple web application deployed using AWS services. The CI/CD pipeline automates the process of building, testing, and deploying the application, ensuring smooth and consistent updates.

## Features
- User registration and login functionality.
- Profile page displaying random user information.
- Home page inspired by Instagram with basic post, like, and comment functionalities.
- Integration with AWS CI/CD tools for automated deployment.

## Tech Stack
- **Frontend**: HTML, CSS, JavaScript
- **CI/CD Tools**: GitHub, AWS CodePipeline, AWS CodeBuild, AWS S3, AWS IAM

## Getting Started
Follow the instructions below to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites
- [AWS Account](https://aws.amazon.com/)
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- [Git](https://git-scm.com/) installed on your local machine

### Setup and Deployment
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/your-repository.git
   cd your-repository

2. Set Up AWS CLI:
Configure AWS CLI with your credentials:
#command to configure AWS on your machine(Laptop)
  aws configure
#Provide your AWS Access Key, Secret Key, region, and output format.

3. Create an S3 Bucket:
  Go to the AWS S3 console and create a new bucket for hosting the web application.
  Enable static website hosting in the bucket settings.

4. Update Bucket Permissions:
  Update the S3 bucket policy to allow public read access to your HTML files.

5. Deploy Using CI/CD Pipeline:
  Push the changes to the GitHub repository.
  The AWS CodePipeline will automatically build and deploy the application to the S3 bucket.

## CI/CD Pipeline
The CI/CD pipeline is set up to automate the deployment process using AWS services:

- GitHub: Source code management and version control.
- AWS CodePipeline: Orchestrates the CI/CD process.
- AWS CodeBuild: Builds the application and prepares it for deployment.
- Amazon S3: Hosts the static web application.
- AWS CloudFront (Optional): Provides content delivery network (CDN) capabilities for enhanced performance and security.

i) Buildspec File
The pipeline uses a buildspec.yml file to define the build steps:
  ##Buildspec code Start
  version: 0.2
phases:
  install:
    commands:
      - echo Installing Dependencies
  build:
    commands:
      - echo Building the application...
      - mkdir dist
      - cp *.html dist/
artifacts:
  files:
    - '**/*'
  base-directory: dist
  ##Buildspec code end

Contributing
Contributions are welcome! Please submit a pull request or open an issue for improvements and suggestions.

### Summary:
- This README covers the core aspects of the project, including its setup, CI/CD pipeline details, and how to get started.
- Adjust and personalize the instructions based on your specific environment and deployment settings.

Let me know if you need further customization or additional sections!
