# 300 Test Your Setup

***NOTE***: Don't use localhost or 127.0.0.1 or "/artifactory"

Due to a limitation in the Docker client, you cannot access an Artifactory Docker registry as localhost or 127.0.0.1. If you need to access a local installation of Artifactory, make sure to specify its full IP address.

In addition, when specifying Artifactory's URL, you should omit the /artifactory suffix normally used.

For example, if your local machine's IP address is 10.1.16.114, then you must specify your Artifactory URL as http://10.1.16.114:8082 (using http://localhost:8082 will not work).

The code snippets below assume you have a virtual Docker repository named ```docker-virtual``` in an Artifactory installation at IP ```10.1.16.114```.

First, you should verify that your Docker client can access Artifactory by run the following command. Making sure that the return code is 200:

```
curl -I -k -v http://10.1.16.114:8082/artifactory/api/system/ping
```

Now you can proceed to test your Docker registry.

- Login to Artifactory as your Docker registry
```
docker login -u admin -p password 10.1.16.114:8082
```

- Pull the hello-world image from the docker-virtual repository
```
docker pull 10.1.16.114:8082/docker-virtual/hello-world:latest
```

- Tag a Docker image
```
docker tag 10.1.16.114:8082/docker-virtual/hello-world:latest 10.1.16.114:8082/docker-virtual/<tag_name>
```

- Push the tagged image to docker-virtual
```
docker push 10.1.16.114:8082/docker-virtual/<tag_name>
```
