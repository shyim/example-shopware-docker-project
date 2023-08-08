# Example Shopware 6 Production Repository

Contains:
- Shopware 6.5.0.0
- Installed Extensions: `frosh/tools` and `frosh/lazy-sizes` (see [composer.json](composer.json))

The repository also contains a GitHub Action which auto deploys the changes


## Run it locally

```bash
# build the image locally
docker build -f docker/Dockerfile -t ghcr.io/shyim/example-shopware-docker-project:latest .

source .env.docker

# start containers
docker compose -f docker-compose.prod.yml up -d

# shopware runs at http://localhost:8000
```