Start n8n:
docker volume create n8n_data
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
http://localhost:5678
https://docs.n8n.io/hosting/installation/docker/#updating
# Pull latest (stable) version
docker pull docker.n8n.io/n8nio/n8n

# Pull specific version
docker pull docker.n8n.io/n8nio/n8n:1.81.0

After pulling the updated image, stop your n8n container and start it again. You can also use the command line. Replace <container_id> in the commands below with the container ID you find in the first command:

# Find your container ID:
docker ps -a

# Stop the container with the `<container_id>`
docker stop <container_id>

# Remove the container with the `<container_id>`
docker rm <container_id>

# Start the container
docker run --name=<container_name> [options] -d docker.n8n.io/n8nio/n8n

Updating Docker Compose#
If you run n8n using a Docker Compose file, follow these steps to update n8n:
# Pull latest version
docker compose pull

# Stop and remove older version
docker compose down

# Start the container
docker compose up -d


https://supabase.com/docs/guides/self-hosting/docker

You should update your services frequently:
- Visit the supabase/studio image in the Supabase Docker Hub
- Find the latest version (tag) number. It will look something like 20241029-46e1e40
- Update the image field in the docker-compose.yml file to the new version. It should look like this: image: supabase/studio:20241028-a265374
- Run docker compose pull and then docker compose up -d to restart the service with the new version.

Securing your services:
cd /c/CyberFlicker/supabase-project
nano /c/CyberFlicker/supabase-project/.env
Change all passwords and keys

After change:
docker compose down -v
rm -rf volumes/db/data/
docker compose up -d

https://github.com/hashicorp/vault
https://hub.docker.com/r/hashicorp/vault
https://developer.hashicorp.com/vault/tutorials/get-started/learn-ui

#ANY_DOCKER_MCP
# Run containers after restart:
docker update --restart unless-stopped container_name

# BASEROW
# To update to the latest run:
docker-compose down
git pull
docker-compose up -d

