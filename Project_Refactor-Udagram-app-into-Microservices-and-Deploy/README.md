# Udagram

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into three parts:

1. [The Simple Frontend](/udacity-c3-frontend):
A basic Ionic client web application which consumes the RestAPI Backend.
2. [The RestAPI Feed Backend](/udacity-c3-restapi-feed), a Node-Express feed microservice.
3. [The RestAPI User Backend](/udacity-c3-restapi-user), a Node-Express user microservice.

Additional resources:
- [Saved Screenshots](assets)
- [Misc scripts](scripts)
- [Deployment](udacity-c3-deployment)

# Starting Udagram (Manually)
## Getting Setup

> _tip_: this frontend is designed to work with the RestAPI backend(s). It is recommended you start up the backend first, test using Postman, and then the frontend should integrate.

### Installing Node and NPM
This project depends on Nodejs and Node Package Manager (NPM). Before continuing, you must download and install Node (NPM is included) from [https://nodejs.com/en/download](https://nodejs.org/en/download/).

### Installing Ionic Cli
The Ionic Command Line Interface is required to serve and build the frontend. Instructions for installing the CLI can be found in the [Ionic Framework Docs](https://ionicframework.com/docs/installation/cli).

### Installing project dependencies

This project uses NPM to manage software dependencies. NPM Relies on the package.json file located in the root of this repository. After cloning, open your terminal and run:
```bash
npm install
```
>_tip_: **npm i** is shorthand for **npm install**

### Setup Backend Node Environment
You'll need to create a new node server. Open a new terminal within the project directory and run:
1. Initialize a new project: `npm init`
2. Install express: `npm i express --save`
3. Install typescript dependencies: `npm i ts-node-dev tslint typescript  @types/bluebird @types/express @types/node --save-dev`
4. Look at the `package.json` file from the RestAPI repo and copy the `scripts` block into the auto-generated `package.json` in this project. This will allow you to use shorthand commands like `npm run dev`


### Configure The Backend Endpoint
Ionic uses environment files located in `./src/enviornments/enviornment.*.ts` to load configuration variables at runtime. By default `environment.ts` is used for development and `enviornment.prod.ts` is used for produciton. The `apiHost` variable should be set to your server URL either locally or in the cloud.

### Running the Development Server
Ionic CLI provides an easy to use development server to run and auto-reload the frontend. This allows you to make quick changes and see them in real time in your browser. To run the development server, open terminal and run:

```bash
ionic serve
```

### Building the Static Frontend Files
Ionic CLI can build the frontend into static HTML/CSS/JavaScript files. These files can be uploaded to a host to be consumed by users on the web. Build artifacts are located in `./www`. To build from source, open terminal and run:
```bash
ionic build
```

# Starting Udagram (Automagically)

```bash
cd scripts
# Script will run all Dockerfiles and build
#bash build_images.sh
# Script will build all docker files and run the respective containers
bash build_docker_compose.sh
minikube start --vm-driver=docker
# Script will configure kubenetes
bash kubenetes_apply_yml.sh
```

# Results

As per screenshot below, this is the results of a successful running project.

# Docker container logs and running pods.
![](https://raw.githubusercontent.com/mmphego/cloud-developer-course3-microservices/master/Project_Refactor-Udagram-app-into-Microservices-and-Deploy/assets/kubectl_pods.png)

# Kubenetes deployment and running pods.
![](https://raw.githubusercontent.com/mmphego/cloud-developer-course3-microservices/master/Project_Refactor-Udagram-app-into-Microservices-and-Deploy/assets/kube_deplo.png)

# Docker Hub Dashboard
![](https://raw.githubusercontent.com/mmphego/cloud-developer-course3-microservices/master/Project_Refactor-Udagram-app-into-Microservices-and-Deploy/assets/docker_hub.png)

# Travis Dashboard
![](https://raw.githubusercontent.com/mmphego/cloud-developer-course3-microservices/master/Project_Refactor-Udagram-app-into-Microservices-and-Deploy/assets/travis_dash.png)

# Travis build status
![](https://raw.githubusercontent.com/mmphego/cloud-developer-course3-microservices/master/Project_Refactor-Udagram-app-into-Microservices-and-Deploy/assets/travis_build_success.png)

# Travis build history
![](https://raw.githubusercontent.com/mmphego/cloud-developer-course3-microservices/master/Project_Refactor-Udagram-app-into-Microservices-and-Deploy/assets/travis_build.png)

## App running on browser

![](https://raw.githubusercontent.com/mmphego/cloud-developer-course3-microservices/master/Project_Refactor-Udagram-app-into-Microservices-and-Deploy/assets/app.png)
