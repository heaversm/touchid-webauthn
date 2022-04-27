# MozAuth Prototype

This prototype uses [WebAuthN](https://webauthn.me/introduction) to enable authentication using TouchID, FaceID, USB Key, and other methods.

WebAuthN allows for strong, attested, scoped, public key-based credentials by web applications. By using this in conjunction with something like Apple's TouchID, FaceID, or other platform authenticator, you have the added benefit of a secure enclave in which to handle sign-on, as well as anonymous attestation which prevents attestation from being used as a tracking vector across websites.

The credentials are stored in a MongoDB instance

## Requirements

1. Download and install [NodeJS 8.9 or newer](https://nodejs.org/en/)
2. Download and install [VS Code](https://code.visualstudio.com/)
3. Download and install [MongoDB Community](https://www.mongodb.com/download-center#community)
4. Clone this repository
5. Open this repository in VS Code
6. Run npm install in the root directory
7. Start MongoDB (if installed with brew, run `brew services start mongodb-community@5.0`)
8. Navigate to [localhost:3000](http://localhost:3000)

## Deploying to Cloud Platform

You'll need both a cloud web instance and DB instance.

Before deploying, you'll need to define the following environment variables inside app services application settings so they can be accessed by this NodeJS app at runtime:

- MONGODB_URL - connection URL to your mongodb. Get it from Cosmos DB settings. Pick the latest Node.js 3.0 connection string under Quick Start.
- JWT_SECRET - some long random string
- HOSTNAME - hostname of your deployed service (e.g. "webauthnsample.azurewebsites.net")
- ENFORCE_SSL_HEROKU - "true"
- WEBSITE_NODE_DEFAULT_VERSION - set to "8.9.4" or newer

This code was modified from an example by [Microsoft and Ibrahim Damlaj](https://github.com/MicrosoftEdge/webauthnsample)
