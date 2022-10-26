# Bamboo

Bamboo is a self-hosted, CI/CD solution developed by **Atlassian** - the company behind applications like *Confluence, Jira, and Bitbucket*. For teams that are using other Atlassian products, Bamboo is a nice fit for adding a CI/CD server to project management and issue tracking workflows. Work assigned in Jira for example, can be directly associated with a pipeline in Bamboo. Bamboo also provides integrations with Bitbucket - Atlassian's source code repository product. 

Bamboo is a paid product, and the pricing ranges from $10 for small teams into the thousands of dollars for larger teams. The pricing scheme is based on the number of jobs available to run and the number of remote agents a Bamboo server can connect to. At the lowest tier, Bamboo can run up to 10 jobs using an agent running on the same server that's running Bamboo. This might be okay for small teams running just a few jobs but larger teams will certainly benefit from isolating the Bamboo server and distributing their jobs over more agents. 

To extend functionality, Atlassian provides a *marketplace* for Bamboo plug-ins. Some plug-ins are free while others have a cost associated with them. 

## Bamboo File Format

Bamboo pipelines are configured in the web user interface and it also supports spec files that can be stored along with the application code. Spec files can be written in *YAML* or *Java* with both of these formats having their benefits. YAML is easy to read and understand, even for someone that might not be familiar with programming. Java might be a bit more complicated to read but is a popular language and many developers are familiar with it. 

## Application

Bamboo pipelines are called *plans*. I've modeled our experimental pipeline in six stages. Most stages have one job. With the 'Check' stage having two jobs that run in parallel to speed up the build. 

One thing that should be noted about these stages is that each one runs in an isolated directory on the server's file system. So each stage needs to check out it's own copy of the code. 

Bamboo provides a specific type of project for deployments. This is useful if our builds produce artifacts that need to be deployed into specific environments. Bamboo has plenty of capabilities on it's own and can do even more when paired with other Atlassian products - e.g. Jira, Confluence, and Bitbucket.
