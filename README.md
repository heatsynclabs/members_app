# Member Management App for Hackerspaces & Makerspaces

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

[![Slack Chat](https://img.shields.io/badge/slack-heatsynclabs-red)](http://bit.ly/hslslack)

This is a meta package for running the entire Members DB nodejs app (i.e. all of its microservices together). It's currently made up of:

 - [members_api](https://github.com/heatsynclabs/api) [![Build Status](https://travis-ci.com/heatsynclabs/members_api.svg?branch=master)](https://travis-ci.com/heatsynclabs/members_api)
 - [members_ui](https://github.com/heatsynclabs/members_ui) [![Build Status](https://travis-ci.com/heatsynclabs/members_ui.svg?branch=master)](https://travis-ci.com/heatsynclabs/members_ui)
 - postgres

## Staging Environment

 - UI: https://hsl-members-ui-staging.herokuapp.com
 - API: https://hsl-members-api-staging.herokuapp.com

## Development Roadmap

[![Project Tracker](https://img.shields.io/badge/kanban-github-blueviolet)](https://github.com/orgs/heatsynclabs/projects/1)

Generally, to be a complete CRM, Billing, Membership, Certification, Inventory, and Ticketing platform, as well as a community hub and self-governance tool for makerspaces and hackerspaces.

To see a semi-complete list of competing software, visit https://wiki.hackerspaces.org/Hackerspace_Software . There are many softwares like it, but this one is ours.

## Normal Docker Dev Usage

First, create a local copy of your docker-compose:
`cp docker-compose.dist.yml docker-compose.yml`

And edit it as desired:
`nano docker-compose.yml`

  > **Warning, this docker image is intended for dev mode** attached to a destroyable Postgres server and npm-install-able project folder. ***Running this in critical/prod environments is strongly discouraged without lots of testing!!!***

Take note of port numbers, DATABASE_URL, SENDGRID_API_KEY, and volume paths. You'll almost definitely have to change the `/path/to/` and maybe `../members_...` paths to fit your environment. Download the necessary repos so you have everything. *If you don't have access to the other repos, contact a maintainer.*

Review the `Dockerfile` in each repo so you know what's about to be booted. For example, the working directory, package.json, and CMD (including npm install and fixture-installation commands) lines which by default will affect your environment since they are mounted via volumes.

Create the docker container for the api, ui, and database:
`docker-compose up`

To access a container's shell prompt, i.e. `members_api`:
`docker exec -it members_api /bin/sh` (or use a helper script like `./docker-bash-api.sh`)

To create basic db tables from within container shell (note this is usually automatically done):
`npm run up`

To view a container's website from the docker host machine: `http://localhost:3005` or `http://localhost:3004`

To access the database directly, use your docker host's `psql` or `pgadmin` client on `localhost:5432` (assuming you've forwarded the port in docker-compose.yml)
