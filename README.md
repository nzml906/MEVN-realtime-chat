# MEVN Chat

Real Time Chat Application created with VueJS, Express, Socket IO and MongoDB/Mongoose/Mongo Altas.

## Demo

View the application at [https://fierce-dawn-90847.herokuapp.com/](https://fierce-dawn-90847.herokuapp.com/)

## Features

- [Express](https://expressjs.com/) as the web framework on the server
- Implements stateless authentication with [JWT](https://jwt.io/) tokens
- Authenticates [JWT](https://jwt.io/)
- Hashes passwords using the [bcryptjs](https://www.npmjs.com/package/bcryptjs) package
- Enables real time communication to the server using [Socket IO](https://socket.io/)
- [MongoDB](https://www.mongodb.com/) and [Mongo Atlas](https://www.mongodb.com/cloud/atlas) is used for storing and querying data
- Server logging is done with [Winston](https://www.npmjs.com/package/winston) and [Morgan](https://www.npmjs.com/package/morgan)
- [Concurrently](https://www.npmjs.com/package/concurrently) is used to run both the server and client at the same time
- [Vue JS](https://vuejs.org/) is used as the frontend framework
- [Travis CI](https://travis-ci.org/) is incorporated for continuous integration
- [Heroku](https://www.heroku.com) is used for production deployment

## Installation

### Running Locally

1. Clone or Download the repository (Depending on whether you are using SSH or HTTPS)

2. Install dependencies for root, client and server

> You will need to npm install in each directory in order to install the node module needed for each part of the project

> Directories Include: Root, Server & Client

3. Add .env file to server folder and fill out details according to the .env.example. See [configuration details](#configuration-setup) for social auth and database setup: **Note, this is mandatory for the application to run**

4. Set **NODE_ENV=development** and **HEROKU_DEPLOYMENT=false**

5. Start the application

```bash
$ npm run dev
```

Your app should now be running on [localhost:8080](localhost:8080).

### Run [Production Ready] Mode

_Ensure [Node.js](https://nodejs.org/en/) and [NPM](https://www.npmjs.com/) are installed_

This runs the application with the built production ready Vue files as well as running the express server in production mode serving up the compiled files.

1. Clone or Download the repository (Depending on whether you are using SSH or HTTPS)

2. Install dependencies for root, client and server

> You will need to npm install in each directory in order to install the node module needed for each part of the project

> Directories Include: Root, Server & Client

3. Add .env file to server folder and fill out details according to the .env.example. See [configuration details](#configuration-setup) for social auth and database setup. **Note, this is mandatory for the application to run**

4. Ensure you set **NODE_ENV=production** and **HEROKU_DEPLOYMENT=false**

5. Start the application in the root folder of the project. Since it's running in production mode, you should not see any message such as: **_"Server started at port 5000"_**

```bash
$ npm run start
```

Your app should now be running on the port you specified in the .env file. If none was specified it will default to **port 5000**.

Eg. [localhost:5000](localhost:5000).

## Running Tests

Tests should be run before every commit to ensure the build is not broken by any code changes.

Running Both Client and Server Tests

```javascript
In the root directory
$ npm run test
```

Running Client Tests

```javascript
$ npm run client:test
```

Watching Server Tests

```javascript
$ npm run server:test:watch
```

## Configuration Setup

These configuration setups are necessary for the app to function correctly as intended. These configuration setups will be required to be added as environment variables for the server to make use of.

### Local Environment Variables (.env file)

For development you will need a .env file for environmental variables.

**_Note: These are required for the application to be setup correctly_**

```bash
NODE_ENV=development
HEROKU_DEPLOYMENT=false

DATABASE_URL=DATABASE_URL

EXPRESS_SESSION_KEY=EXPRESS_SESSION_KEY
JWT_SECRET=JWT_SECRET

PORT=PORT
```

### MongoDB & Mongo Atlas

A MongoDB URI is needed to connect to a MongoDB connection. The easiest way to do this is to use [Mongo Atlas](https://www.mongodb.com/cloud/atlas). If you'd like to do this locally you can follow the instructions at (https://docs.mongodb.com/manual/installation/)

#### Mongo Atlas

1. Select 'Build a New Cluster' and follow the prompts

2. When the Cluster has been created, click on 'Connect'

3. Choose your connection method, for the purposes of this application we will use 'Connect Your Application'

4. Next you will need to grab this connection string (Standard connection string). This is the URI that will be used as an environment variable

### JWT Secret

The JWT Secret is required as a way to keep the JWT Token secure when the signature is hashed. This secret key should be secret to you and should be updated periodically.
