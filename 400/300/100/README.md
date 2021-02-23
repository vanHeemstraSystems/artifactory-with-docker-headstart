# 100 Configuring Artifactory

To configure Artifactory to use the Repository Path method, carry out the following steps:

1. Make sure Artifactory is up and running, and is activated with a valid license. 

2. Create your [virtual Docker repository](https://www.jfrog.com/confluence/display/JFROG/Docker+Registry) (as well as a local and remote Docker repository that it should aggregate). In our example below we will use a repository named ```docker-virtual```. 

3. Go to the ***HTTP Settings*** page from the ***Administration*** module under ***Artifactory | General | HTTP Settings***. In the ***Docker Settings*** panel, select ***Repository Path*** as the Docker Access Method. In the ***Reverse Proxy Settings*** panel select ***Embedded Tomcat*** as the Server Provider (which indicates you're not using a reverse proxy). 

***NOTE***: You must use Embedded Tomcat

You can only use Artifactory as a Docker registry without a reverse proxy by using the internal embedded Tomcat.
