# CICD

## Continuous Integration

* A software development practice to make sure new integrations don't break the code.
* Automated process.

### Goals

* Automate the build.
* Make build self-testing.
* Make sure new commits don't break the code.
* Keep the build fast.

### Process

* The CI tools watches repository for changes.
* Once the code is pushed to the repository automatic build is triggered.
* CI server notifies the team on successful builds and failure builds.

## Continuous Deployment

* The next part after CI.
* Automating the process of Deployment.
* By doing Pre deployment and Post deployment processes automatically for safety.

### Goals

* Automate the deployment.
* To safely/smoothly deploy the application without problems.
* Save time time for the engineering team by automating deployment.

### Process

* After a successful build the user acceptance testing is done the code is merged to the main branch.
* After merge into main branch the build process is triggered once again.
* After the build is done the Pre deployment processes are done things such as DB backup, cleaning the dependencies etc.
* After Pre deployment process the Production Application is deployed into the server.
