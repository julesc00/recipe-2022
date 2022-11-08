# Recipe API Project with Django
By Mark Winterbottom, updated 2022 at [Udemy](https://www.udemy.com/share/101XNg3@tuT16TYj7R-4hDIMSBy7HolRpDUVJzu7JBaa28n3xlswfSiC6reE6-Y6qlGH1UIROQ==/)

## Dockerhub and Github Configuration
1. Create an account at dockerhub.
2. Once logged into Dockerhub, go to Account Settings > Security > New Access Token. Save this access token somewhere safe.
3. At Github, create a new repository > Settings > Secrets > Create two new secrets: `DOCKERHUB_USER` with the Dockerhub username.
4. ...continued: `DOCKERHUB_TOKEN` and paste the token here.

## Docker Configuration
1. Create a Dockerfile
2. List steps for creating the image:
    - Choose a base image (Python)
    - Install dependencies
    - Setup users

## Using Docker Compose
- Run all commands through Docker compose
- `docker-compose run --rm app sh -c "python manage.py runserver"`
### Explanation
- `docker compose` **runs a Docker Compose command**
- `run` **will start a specific container defined in config**
- `--rm` **removes the container**
- `app` **is the name of the service**
- `sh -c` **passes in a shell command**

## Create the requirements.txt file
1. Do this in the project root directory.
2. Create the **app** directory in the root directory

## Create the Dockerfile and build image
1. Once created, run: `docker build .`

## Create the docker-compose.yml configuration file