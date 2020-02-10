# CICD pipeline with AWS codepipeline

## Tools

* Bitbucket
* AWS Codepipeline.
* AWS EC2
* AWS CodeDeploy (not sure yet)

## Steps

1. Create your pipeline and choose the connection.
2. Create a source stage (Bitbucket) and connect to bitbucket.

## Process

Developer --> Bitbucket --> AWS codepipeline --> AWS EC2 Instance

## Advantages

* No maintaincence.
* Simple setup.
* No integration problem with aws products.
* Parallel Execution.

## Disadvantages

* Since pieces of CI/CD processes are divided into different services, it might cost more based on what all services we want to use.(CodeCommit(Repo manager), CodeBuild(CI tool), CodePipeline(CD tool), CodeDeploy(Deployment tool)).

## Pricing

* It is based on number of active pipelines.
