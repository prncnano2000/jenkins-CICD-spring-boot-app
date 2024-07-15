|| [Prerequisites](#prerequisites) ||
[Deployment](#deployment) ||
[Authors](#authors) ||

# jenkins-CICD-spring-boot-app

![alt text](<CICD Jenkins.png>)

This project demonstrates how to configure a `CI/CD pipeline` using Jenkins for a `Spring Boot` application containerized with Docker. We will also configure `SonarCloud` for code quality analysis and use `MySQL containers` for staging and production environments.

Pipeline structure:

Retrieving the code ==>
 Building the Docker image ==>
 SonarCloud code analysis ==>
 Unit tests ==>
 Deployment in Staging ==>
 Integration tests ==>
 Deployment in Production ==>
 Monitoring.



## Technologies


- [Docker](https://www.docker.com/get-started)

- [Jenkins](https://www.jenkins.io/download/)

- [Git](https://git-scm.com/downloads)

- [SonarCloud](https://sonarcloud.io/)

- [Maven](https://maven.apache.org/download.cgi)



## Features



- `Checkout`: Retrieving the source code from the Git repository.

- `SonarQube Analysis`: Analysis of code quality with SonarCloud.

- `Build Docker Images`: Construction of Docker images for the Spring Boot application and the MySQL database.

- `Test`: Execution of unit tests.

- `Push to DockerHub`: Pushing Docker images to DockerHub.

- `Deploy to Staging`: Deployment of containers to the staging environment.

- `Deploy to Production`: Deployment of containers to the production environment.


  
## Prerequisites


- A running Jenkins server.

- Docker installed on your Jenkins server.

- A GitHub account to store your spring boot application code.

- have a sonarcloud account

  
## Installation



In your command prompt download the repo with the commands:
```bash
  git clone https://github.com/AnselmeG300/jenkins-CICD-spring-boot-app.git

  cd jenkins-CICD-spring-boot-app
  
  code . 
```

    
## Deployment


1. **Create a `Git repository` for your application**:

 a - Create a `new Git repository` on GitHub or another code hosting provider.

 b - Clone the repository on your development machine.

 c - Add your code files to the Git repository and make commits.


2. **Configure Jenkins**:

 a - Access the Jenkins web interface.

 b - Create a new project (job) by selecting `New project`.

 c - Add your `DockerHub credentials` to Jenkins Credits.

 d - Add your `SonarCloud token` to Jenkins Credits:

   - Configure SonarCloud: In Jenkins, go to "Manage Jenkins" > "Configure System" and add SonarCloud under "SonarQube Servers".


 e - Give your project a name, for example `PayMyBuddy`.

 f - Select `Git` as `version control system`.

 g - Enter the `Git repository URL` of your application.

 f - Set Git credentials if necessary.



3. **Create a build pipeline**:

 a - Select the `Pipeline` tab.

 b - Click on `New pipeline`.

 c - Choose `Pipeline Scripted`.

 d - Paste the `Jenkinsfile` script from this git repository into the script editor.



4. **Save and run the pipeline**:

 a - Save the Jenkins pipeline.

 b - Start the pipeline `manually` or configure a trigger to run `automatically` every time you push code to the Git repository.


A. `Manually deployed`:
- Access the Jenkins web interface.
- Select your spring boot project.
- Click the “Build Now” button to launch the pipeline manually.

B. `Automatic deployment`:
- Configure a webhook in your code hosting provider (GitHub, GitLab, etc.) to send a notification to Jenkins whenever you push code to the repository.
- Jenkins will automatically trigger the pipeline when it receives a webhook notification.

**```Conclusion```**

You now have `a working CI-CD pipeline` for a `Flask` ​​application using `Jenkins and Docker`. This pipeline will build your Docker image, run tests, push the image to DockerHub and deploy the application to the staging or production environment.



 For more details, see the following video: [Jenkins-CI-CD-spring-boot-app](https://youtu.be/0R0g8xvpgtM?si=jxs63dXDIZpRINLj)


## Authors

- [@AnselmeG300](https://github.com/AnselmeG300/terraform-cloud.git)


## License

[MIT](https://choosealicense.com/licenses/mit/)


## Badges

Add badges from somewhere like: [shields.io](https://shields.io/)

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)
