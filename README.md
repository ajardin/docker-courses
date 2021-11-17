# Docker courses

> This repository explains how Docker Compose works with web application thanks to a Symfony application as an example.
> Docker and Docker Compose are the only requirements to run the project: PHP is not needed.

## Installation

```
git clone git@github.com:ajardin/docker-courses.git

# Fix remaning "TODO" instructions

docker-compose up --detach
docker-compose exec php sh -c "composer install --optimize-autoloader"

# The Symfony application is now accessible from your browser with:
#     - 127.0.0.1, if you use Linux or Docker Deskptop on Windows or macOS.
#     - 192.168.99.100, if you use Docker Toolbox. 
```
