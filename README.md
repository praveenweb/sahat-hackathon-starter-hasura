# sahat-hackathon-starter

git push and deploy this [sahat/hackathon-starter](https://github.com/sahat/hackathon-starter) to an HTTPS domain.

This project is a Node.js boilerplate for deploying to the cloud using Hasura. Make changes and “git push” to automatically build a docker image and deploy using kubernetes. Comes with MongoDB, Bootstrap 3 + SaaS, Contact Form, Profile Management, a Node.js Dockerfile and Kubernetes spec files. This can be deployed on Hasura’s free hosting tier.

## Deployment instructions

### Basic deployment:

* Press the **Clone & Deploy** button and follow the instructions.
* The `hasura quickstart` command clones the project repository to your local computer, and also creates a **free Hasura cluster**, where the project will be hosted for free.
* A git remote (called hasura) is created and initialized with your project directory.
* Run `git add .`, `git commit`, and `git push hasura master`.
* Run the below command to open your deployed starter kit.
``` shell
$ hasura microservice open www
```

### Making changes and deploying

* To make changes to the project, browse to `/microservices/www/src` and edit the source code as required.
* Commit the changes, and perform `git push hasura master` to deploy the changes.

### Configuring Environment Variables

This boilerplate comes with a bunch of configurable environnment variables. Edit k8s.yaml file inside microservices/www directory and add the required values.

## View server logs

You can view the logs emitted by the ‘serve’ package by running the below command:

``` shell
$ hasura microservice logs ui
```
You can see the logs in your terminal, press `CTRL + C` to stop logging.

## Managing app dependencies

* System dependencies, like changing the web-server can be made in the Dockerfile
* npm/yarn deps can be managed by editing **package.json**.

If changes have been done to the dependencies, `git commit`, and perform `git push hasura master` to deploy the changes.
