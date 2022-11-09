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

## Configure Linting and Testing
1. Install flake8 package by adding a **requirements.dev.txt** file.
2. To run flake8: `docker-compose run --rm app sh -c "flake8"`
3. For testing we'll use Django unittest, to run: `docker-compose run --rm app sh -c "python manage.py test"`
4. Re-run build: `docker build .`

## Create and start Django project
1. Create the Django project locally with docker-compose: `docker-compose run --rm app sh -c "django-admin startproject app ."`
2. To start the project: `docker-compose up`
3. To stop the sever, press ***ctrl + c***

## Configure Github Actions
- Automation tool
- Similar to Travis-CI, GitLab CI/CD, Jenkins
- Run jobs when code changes
- Automate tasks

### Common uses
- Deployment
- Code linting
- Unit tests

### Configuration
- Create a config file at ***.github/workflows/checks.yml***
  - Set trigger
  - Add steps for running testing and linting
- Configure DockerHub auth
  - Use `docker login` during our job
  - Add secrets to GitHub project (which I already did)