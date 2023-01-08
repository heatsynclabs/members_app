# Member Management App for Hackerspaces & Makerspaces

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![Slack Chat](https://img.shields.io/badge/slack-heatsynclabs-red)](http://bit.ly/hslslack)

This is a meta package for running the entire Members DB nodejs app (i.e. all of its microservices together). It's currently made up of:

 - [members\_api](https://github.com/heatsynclabs/members_api)
 - [members\_ui](https://github.com/heatsynclabs/members_ui)
 - postgres

## Staging Environment

 - UI: https://hsl-members-ui-staging.herokuapp.com
 - API: https://hsl-members-api-staging.herokuapp.com

## Development Roadmap

[![Project Tracker](https://img.shields.io/badge/kanban-github-blueviolet)](https://github.com/orgs/heatsynclabs/projects/1)

See our [Wiki](https://wiki.heatsynclabs.org/wiki/HSL_API) for project governance, and each repo's CONTRIBUTING file for how to help out.

The project's goal is generally to be a complete CRM, Billing, Membership, Certification, Inventory, and Ticketing platform, as well as integrating with an open source RFID Door Access system, and providing a community hub and self-governance tool for makerspaces and hackerspaces. We aim to accomplish this by creating moderately-sized microservices (miniservices?) that can interoperate across a wide range of member projects while still providing a functioning and maintainable base service.

To see a semi-complete list of competing software, visit [the Hackerspaces Wiki](https://wiki.hackerspaces.org/Hackerspace_Software). There are many softwares like it, but this one is ours.

## Usage

Visit the API and UI repos. Clone both projects to your local machine and follow the READMEs to spin them up.
