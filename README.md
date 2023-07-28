# Deploying an Angular application within nginx:alpine docker

## Dockerizing the app
export TAG="YOUR_TAG"
docker build -t "$TAG" .

## Publishing the app to ghcr.io
docker tag $(docker image ls | grep "$TAG" | awk '{print $3}') ghcr.io/USERNAME/YOUR_TAG:latest

docker push ghcr.io/USERNAME/YOUR_TAG:latest

## Notes
Adapt the Dockerfile as needed to reflect the path to your built application (default: "dist/my-app/").
A custom nginx config is provided which requires no further configuration.
