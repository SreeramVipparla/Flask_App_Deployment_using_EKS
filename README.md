# Flask App Deployment using EKS Project

# Overview

<img src="https://user-images.githubusercontent.com/86887626/142653189-19f9611e-b710-49bc-b3de-1b3655987100.jpg" width="1000" height="250">

# Introduction

In this project I have created a JWT Token generator which is containerized using Python.The project relies on a secret set as the environment variable `JWT_SECRET` to produce a JWT.I have deployed the Flask app to a Kubernetes cluster using Docker and AWS EKS.

The Flask app that will be used for this project consists of an API with three endpoints:

- `GET '/'`: This is a simple health check, which returns the response 'Healthy'.
- `POST '/auth'`: This takes a email and password as json arguments and returns a JWT based on a custom secret.
- `GET '/contents'`: This requires a valid JWT, and returns the un-encrpyted contents of that token.

The project relies on a secret set as the environment variable `JWT_SECRET` to produce a JWT. The built-in Flask server is adequate for local development, but not production, so you will be using the production-ready [Gunicorn](https://gunicorn.org/) server when deploying .

# Dependencies

- Docker Engine
  - Installation instructions for all OSes can be found [here](https://docs.docker.com/install/).
  - For Mac users, if you have no previous Docker Toolbox installation, you can install Docker Desktop for Mac. If you already have a Docker Toolbox installation, please read [this](https://docs.docker.com/docker-for-mac/docker-toolbox/) before installing.
- AWS Account
  - You can create an AWS account by signing up [here](https://aws.amazon.com/#).

## ENV_FILE CONTENTS

JWT_SECRET='myjwtsecret'
LOG_LEVEL=DEBUG
