# 200 Configuring Your Docker Client

Using the Repository Path method, you can work with Artifactory as a Docker registry without a reverse proxy on an insecure connection (i.e. only HTTP is supported, not HTTPS). ***You need to configure the Docker client to work with an insecure registry*** as described in the Docker documentation.

Restart your Docker daemon/engine to apply the insecure registry flag (if self-signed certificate is imported, you do not need to restart the Docker daemon/engine). Running ```$ docker info``` will list the Insecure registries that have been applied under the Insecure Registries entry. 
