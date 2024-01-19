# Autogen Studio Docker Image

This repository contains a Dockerfile which can be used to build a Docker Image for Autogen Studio using Docker Compose.

## Building the docker image

To build the docker image, run the following commands in the root of this repository:

You will need your OpenAI API token (https://platform.openai.com/api-keys) and save it to ./openAi-token, ensuring to  make it secure.

```bash
echo "Put Your OpenAi API Token Here" >>  ./openAi-token
sudo chown root:root ./openAi-token
sudo chmod 400 ./openAi-token
```

To build the docker image, run the following command in the root of this repository:

```bash
sudo docker build -t autogenstudio-dockercompose --secret "id=openAi-token,src=./openAi-token" .
```
## Edit the Docker Compose file for your requirements

```bash
nano compose.yaml
```

## Running the docker image

To run the docker image, run the following command:

```bash
docker compose up -d
```

The Autogen Studio will be available at http://0.0.0.0:8081 or the port of your choice if you edited compose.yaml accordingly.
