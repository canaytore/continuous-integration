# Jenkins

Jenkins is likely the first to come to mind when thinking of tools for continuous integration. More then 1M users around the world turn to Jenkins for their automation needs, including continuous integration and delivery. Price is one of the reasons that keep application developers and software engineers turning to Jenkins. It's free and open source. Enterprise support for Jenkins is available through *CloudBees* - the company founded by the original creator of Jenkins. 

*CloudBees* is also one of the largest contributors to the Jenkins opensource project. Jenkins is essentially an automation framework that can be extended through plugins. If the base functionality doesn't cover what we need there's probably a plugin that can do the job for us. There are nearly 2,000 plugins available in the plugin index. For instance, *Blue Ocean* plugin is actually a collection of plugins that enhances the Jenkins user interface, specifically for visualizing pipelines. Jenkins includes a pipeline viewer out of the box but *Blue Ocean* provides a more modern and up to date interface. With a clear pipeline is code format and extensive plugin library and pipeline visualizations with *Blue Ocean* plugin, Jenkins remains a viable tool for continuous integration.

## Jenkins File Format

We can model our pipeline in the Jenkins web interface or with a Jenkins file stored with our code. The Jenkins file format is based on the *Groovy* programing language and uses a declarative approach to describe the stages of a pipeline and the actions needed to complete the stage. 

With each configuration element working out into bracketed sections. 

At the top we have environment details that inject our AWS credentials into the process running our pipeline. So that the credentials are exposed as environment variables. The actual values of the credentials are stored securely in Jenkins so they aren't exposed here. 

## Application

Beneath that, we have our stages. I've modeled our experimental pipeline to follow the 7 stages used to get the application code and run some quick tests, build a new version of application and then deploy and test in the staging and production environments. Each of our stages contains the steps that actually run the commands or scripts needed to fulfill the actions for that stage. 

In the 'Check' stage I've used the parallel directive to tell Jenkins to run the lenting and unit test at the same time. Using parallel steps will help speed up the build.
