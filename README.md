# CI/CD Tools

*Continuous Integration, Continuous Delivery, and Continuous Deployment* are fundamental concepts in modern software development. More commonly known as CI/CD, technologists of all kinds use these automated approaches to produce applications efficiently and reliably. The process is often described as a *pipeline*, representing the flow of code and artifacts as they move through the different steps required to build, test, and deploy a complete application. Because this process is so important, there are dozens and dozens of CI/CD tools available, and often finding the right tool can be difficult.

*In this repo, I will be trying to see how an experimental pipeline gets implemented in several different CI/CD applications.*

## Continuous Integration

With CI, developers work on their code in a local environment and commit their changes to a shared repository on a regular basis. Their code can then be combined or, in other words, integrated with code from other members of the team or any existing code. The new code is tested along with existing code and checked for errors. Using this method, developers can find and resolve problems more quickly compared to waiting until all the code for an application is complete and integrating everything at once. 

## Continuous Delivery 

Continuous delivery is a partner to the continuous integration process. Continuous delivery enables developers to build, test, and release their software with every new change. By including tests in the delivery process, engineers can be confident that the final product meets requirements and doesn't have any unintended features, also known as 'bugs'. Once the application is delivered, it can be deployed as needed. When a deployment completes without human interaction, it's referred to as continuous deployment. In this case, the application is automatically built, tested, and deployed into a production environment.

### 1. Self-hosted (e.g. Jenkins, Bamboo, TeamCity, GoCD)

Self-hosted tools run on our hardware. This could mean the tool runs on a server in the company's data center, a VM in the cloud, or it could be on our local workstation. Regardless of the platform, we are responsible for installing the tool and maintaining it. 

It gives us the most flexibility in comparison to any other option. We can specify the entire technology stack, including the software, the hardware, and the network. We also have more control over any data that flows into or out of the tool. We won't have to worry as much about unexpected data leaks or potentially harmful exposures. That flexibility and peace of mind comes at a price though. Since we own the entire technology stack, we also have to maintain it, this can be difficult if we don't have the time or the inclination to install and administer a full blown CI/CD system along with our normal duties. We could also be bounded by the skill of the infrastructure we have on hand. If all of a sudden, we need to increase the throughput of our pipelines, we'll be limited to the capacity of our existing system. Also, getting started with self-hosted tools can be intimidating for the uninitiated, causing difficulties with bringing resources online.

### 2. SaaS (e.g. TravisCI, Codeship, CircleCI)

Tools that fit into the software as a service or SaaS category, offer an alternative to self-hosting. In this case, a vendor provides and maintains the tool and allows us to access it. 

SaaS tools do their best to make it super easy to get started. All the heavy lifting of maintaining the tool is abstracted away and all we need to do is worry about coding our application. There are also plenty of free or reasonably priced SaaS CI/CD services available. SaaS CI/CD tools could create triggers from our repo automatically. SaaS tools might be free or have low fees to start, but they can become expensive over time. There may security concerns when running our data through a system that could be maybe even on the other side of the world (however; security vulnerabilities have the potential to pop up in all of these systems)

### 3. Cloud Service Providers (e.g. AWS CodePipeline - CodeBuild, Azure Pipelines, GCP Cloud Build)

This category is an extension of the software as a service category, cloud service providers offer SaaS-based CI/CD tools but they also offer other cloud-based services like virtual machines, container registries, and cloud storage. 

Cloud Service Providers have unlimited resources and we'll be more likely to use their other cloud services. With easy integration, it just makes sense to keep everything under the same roof. And along with the additional resources, Cloud Service Providers may offer better control over who's viewing our projects and more. Using Identity and Access Management (IAM), we'll be able to control who can push code to our repos and start appointments.

### 4. Code Repositories (e.g. GitHub Actions, GitlabCI, Bitbucket Pipelines)

If we think of a code repository, we first thought is probably of a place where we could store our code. But along with giving us a place to track and manage our code, many modern repositories also provide CI/CD tools for turning that code into software.

Code Repositories have the unique position of having our code and the CI/CD tool all in one place. We might also be able to create custom docker containers to run our build and there are plenty of free or low fee options to get started. One downside though is that CI/CD services based in Code Repositories can get expensive, when used at larger scales.
