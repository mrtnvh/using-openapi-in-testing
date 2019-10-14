# Using OpenAPI in Testing

- [Using OpenAPI in Testing](#using-openapi-in-testing)
	- [Requirements](#requirements)
	- [Installation](#installation)
	- [Run](#run)
		- [1. npm](#1-npm)
		- [2. WIP - Advanced JavaScript](#2-wip---advanced-javascript)
		- [3. Docker](#3-docker)
	- [Tests](#tests)

## Requirements
- Node v10+
- NPM v6+
- Docker

## Installation
```sh
npm install
```

## Run
This example contains 2 processes:
1. A [Nuxt.js](https://nuxtjs.org/) ([Vue.js framework](https://vuejs.org/)) application.
2. A [Prism](https://stoplight.io/p/docs/gh/stoplightio/prism) mocking server.

There are several scenario's of how you can run de example code:

### 1. npm
Start up both processes through npm.
```sh
npm run dev:all
```

Run only the Nuxt.js application.
```sh
npm run dev
```

Run only the Prism mock.
```sh
npm run mocks

# With a watcher on the OpenAPI document
npm run mocks:watch
```

### 2. WIP - Advanced JavaScript
If the default Prism functionality doesn't meet your requirements, you could run Prism programmatically and plugin on the Fastify server Prism
```sh
npm run mocks:advanced

# With a watcher on the OpenAPI document
npm run mocks:advanced:watch
```

The command will run the `mocks/prism.js` with Node.

### 3. Docker
Prism also provides a [Docker image](https://stoplight.io/p/docs/gh/stoplightio/prism/docs/getting-started/installation.md#docker) on which you can mock your OpenAPI document.

```sh
docker run --rm -it -p 4010:4010 -v $(pwd):/tmp stoplight/prism:3 mock -d -h 0.0.0.0 "mocks/prism.js"
```

## Tests
This example uses [Cypress](https://www.cypress.io/) for integration/e2e

Start the Cypress UI
```sh
npx cypress open
```

Run the Cypress
```sh
npx cypress open
```

All Cypress related files are located in the `cypress` folder.
