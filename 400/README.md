# 400 Artifactory On-Prem

Setup your on-prem installation of Artifactory Pro to work with Docker. The Docker client requires a different hostname for each registry. Artifactory supports this whether you are using a reverse proxy or not. 

[Get Started with Artifactory Pro On-Prem](https://www.jfrog.com/confluence/display/JFROG/Getting+Started+with+Artifactory+as+a+Docker+Registry#GettingStartedwithArtifactoryasaDockerRegistry-GettingStartedwithArtifactoryProOn-Prem) >

## 100 Getting Started with Artifactory Pro On-Prem

The Docker client has the following two limitations:

1. You cannot use a context path when providing the registry path (e.g localhost:8082/artifactory is not valid)
2. Docker will only send basic HTTP authentication when working against an HTTPS host or when using the insecure registry flag

Artifactory offers solutions to these limitations allowing you to create and use any number of Docker registries.

## 200 Using a reverse proxy

See [README.md](./200/README.md)

When used, a reverse proxy, maps Docker commands to one of the multiple Docker registries in Artifactory

## 300 Without a reverse proxy

See [README.md](./300/README.md)

From version 5.8, Artifactory supports using Docker without the use of a reverse proxy allowing you to create and use multiple Docker registries in Artifactory out-of-the-box. 
