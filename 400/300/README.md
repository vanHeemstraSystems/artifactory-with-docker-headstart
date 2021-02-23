# 300 Without a reverse proxy

Previously, Artifactory supported the Ports and Subdomain methods described above when using a reverse proxy. From ***version 5.8.*** Artifactory introduces a new method referred to as the "Repository Path" method since it uses the the Docker repository path prefix (<REPOSITORY_KEY/IMAGE>) to access a specific Artifactory Docker registry from the Docker client. Note that you may still have a reverse proxy configured for Artifactory for other reasons, however when configured to use Repository Path method, requests to Docker registries in Artifactory will be handled by Artifactory's embedded Tomcat instead of the reverse proxy.

***NOTE***: Docker API v2 required

You can only use the Repository Path method with Artifactory Docker registries configured for Docker API v2. 

***NOTE***: Sub-domain method is recommended for production

We recommend using the [Sub-domain method](https://www.jfrog.com/confluence/display/JFROG/Getting+Started+with+Artifactory+as+a+Docker+Registry#GettingStartedwithArtifactoryasaDockerRegistry-TheSubdomainMethod) for Artifactory Docker registries in production systems because this method allows you to add wildcard SSL certificates on the reverse proxy for secure access to the [Docker registry](https://www.jfrog.com/confluence/display/JFROG/Docker+Registry). 

While you can add SSL certificates at the Tomcat level, this is not a recommended practice because the process of validation against the certificate is very resource intensive on memory and CPU. 

The Repository Path method is more suitable when secure access is not required. 

## 100 Configuring Artifactory

See [README.md](./100/README.md)

## 200 Configuring Your Docker Client 

See [README.md](./200/README.md)

## 300 Test Your Setup 

See [README.md](./300/README.md)
