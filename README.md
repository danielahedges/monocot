# Monocot

[![Run Status](https://api.shippable.com/projects/5b116041ddd0cc0600eb56b4/badge?branch=master)](https://app.shippable.com/github/danielahedges/monocot)
[![Known Vulnerabilities](https://snyk.io/test/github/danielahedges/monocot/badge.svg)](https://snyk.io/test/github/danielahedges/monocot)

Seed project for a MEAN site, with user authentication, testing, material design
look and feel, and CI/CD.

## Installation Instructions

There are two ways to run the application:

1. "Run Local", where the database and app are both served from your local
   machine
1. "Containers", where the app is deployed in a Docker container, connected to a
   separate database container. Both containers run on your machine.

### Run Local

1. Install [Git](https://git-scm.com/downloads)
1. Download this repo.
1. Install [Node](https://nodejs.org/en/download/), at least version 10.1.
1. Install [MongoDB](https://docs.mongodb.com/manual/installation/)
1. Run a local database instance from a terminal: `mongod`
1. Clone this repository, and cd into the directory.
1. `npm install`
1. `npm run build`
1. `npm start`
1. Open a browser to http://localhost:3000/.

### Containers

For a container deployment, you do not even need to install node on your
machine. The web server will be deployed onto a docker container image that
already has node installed.

1. Install [Git](https://git-scm.com/downloads)
1. Download this repo.
1. Install [Docker](https://docs.docker.com/install/)
1. `docker image build -t monocot .`
1. `docker-compose up -d staging-deps`
1. Open a browser to http://localhost:3000/.
1. To shut down, `docker-compose down`

## Deployment

You can easily deploy onto Heroku for free, just follow these instructions.
Other cloud providers are similar.

1. Create a mongodb instance. [mLab](https://mlab.com) is a good resource.
1. Create a [heroku app instance](https://dashboard.heroku.com/apps).
1. Put the mongo connection string into the environment variable
   `MONGODB_CONNECT` using the following command: `heroku config:set MONGODB_CONNECT=[mongo_connect_url]`.
1. Set `NODE_ENV`: `heroku config:set NODE_ENV=development`.
1. Deploy by following the instructions in your heroku app dashboard. (You will
   add heroku to the git remotes, then push to it).

## Customization

1. In `README.md`:

* Update the project name at the top.
* Get new badges from shippable and update them.
* Update the image name in the `docker image build` command.

1. In `Makefile`:

* Update the docker image name.

1. In `docker-compose.yml`:

* Update the image name in `staging-deps` section.

1. In `package.json`:

* Update name, version, description, repository url.
* Update build image name in the `build` script.

1. Update all config files in `src/core/server/confing/env` with the new db name.
1. Update the title in `src/core/server/controllers/index.server.core.ctrl.js`.
1. Update the test with the new title in
   `src/core/server/controllers/test/index.server.core.ctrl.spec.js`.
1. Pick a better color for the nav bar in `src/core/views/layout.pug`.

