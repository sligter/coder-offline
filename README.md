# coder-offline
Unofficial image for running Coder in offline / private / air-gapped networks.

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
docker run -itd -p 3000:3000 --name coder coder-offline:v0.3 --access-url=http://0.0.0.0:3000 --http-address=0.0.0.0:3000
```
## Docker run with pgsql
```
docker run -itd -p 3000:3000 --name coder coder-offline:v0.3 --access-url=http://0.0.0.0:3000 --http-address=0.0.0.0:3000 --postgres-url postgres://postgres:username@localhost:5432/database?sslmode=disable
```
