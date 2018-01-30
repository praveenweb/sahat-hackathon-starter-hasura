# sahat-hackathon-starter

git push and deploy this [sahat/hackathon-starter](https://github.com/sahat/hackathon-starter) to an HTTPS domain *without any setup*.

This project is a Node.js boilerplate for deploying to the cloud using Hasura. Make changes and “git push” to automatically build a docker image and deploy using kubernetes. Comes with MongoDB, Bootstrap 3 + SaaS, Contact Form, Profile Management, a Node.js Dockerfile and Kubernetes spec files. There is no configuration required to get this nodejs + mongodb app working apart from the "Clone & Deploy" instructions. This can be deployed on Hasura's free hosting tier and should take you all of 2 mins to get up and running.

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

## Managing MongoDB

mongoDB is running as a microservice in the subdomain `mongo` of your cluster. Your mongo server is not exposed to the outside world. To access the mongo shell, execute the following commands:

``` shell
hasura ms exec -it mongo -- bash
```

Once you are inside bash, execute the following command to start using mongo

```shell
mongo
```

Now you are inside mongo shell. You can now start executing mongo commands in this shell. For example:

```shell
show dbs;
```

![Accessing Mongo Shell](https://raw.githubusercontent.com/praveenweb/sahat-hackathon-starter-hasura/master/assets/mongo-shell-access.png)

## View server logs

You can view the logs emitted by the ‘node’ server by running the below command:

``` shell
$ hasura microservice logs www
```

You can view the logs emitted by the ‘mongodb’ database by running the below command:

``` shell
$ hasura microservice logs mongo
```

You can see the logs in your terminal, press `CTRL + C` to stop logging.

## Managing app dependencies

* System dependencies, like changing the web-server can be made in the Dockerfile
* npm/yarn deps can be managed by editing **package.json**.

If changes have been done to the dependencies, `git commit`, and perform `git push hasura master` to deploy the changes.

## Configuring and Extending

This is an unmodified fork of [sahat/hackathon-starter](https://github.com/sahat/hackathon-starter) with a readily deployed Node.js and MongoDB servers. For any documentation on configuring / extending, you can refer to the original repo.
