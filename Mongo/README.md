# How to set up mongo container in Ubuntu EC2 server

## Set up procedure

1. Configuring docker
   Set up docker with referring [docker set up manual](../Docker/README.md)

2. Creating directory for the volume mounted by mongodb in container

   ```bash
   mkdir data
   ```

3. Creating docker-compose.yml file referring [docker-compose.template.yml](./docker-compose.template.yml)

4. Run docker

   ```bash
   docker compose up -d
   ```