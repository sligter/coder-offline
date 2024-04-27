# coder-offline
Unofficial image for running Coder in offline / private / air-gapped networks.

This is an unofficial Docker image designed to run Coder in offline, private, or air-gapped networks where direct access to the internet or public Docker registries is not available. This image includes all the necessary components and dependencies for Coder to function properly in such isolated environments.

By using this image, you can deploy and manage Coder instances without relying on external resources or connectivity to the internet. It provides a self-contained solution for running Coder within your local network or air-gapped infrastructure, ensuring maximum security and control over your development environments.

Note that this image is not an official release from Coder Technologies, Inc. It is a community-maintained solution aimed at addressing the specific needs of organizations operating in offline or air-gapped scenarios. Use it at your own risk, and always refer to the official Coder documentation for the latest updates and best practices.

## Out of the box, this image includes the following bundled software:
- Coder v2.9.4
- Terraform CLI v1.6.6
- Terraform provider: coder/coder provider v0.21.0
- kreuzwerker/docker provider v3.0.2
- KUBERNETES_PROVIDER_VERSION 2.23.0
- AWS_PROVIDER_VERSION 5.19.0

# Usage
``` docker pull ailxy/coder-offline:v0.3 ```

## Docker run without pgsql
```
docker run -itd -p 3000:3000 --name coder coder-offline:v0.3 --access-url=http://ip:3000 --http-address=0.0.0.0:3000
```
## Docker run with pgsql
```
docker run -itd -p 3000:3000 --name coder coder-offline:v0.3 --access-url=http://ip:3000 --http-address=0.0.0.0:3000 --postgres-url postgres://postgres:username@localhost:5432/database?sslmode=disable
```
