# moleculer-mongo-checker

This project provides health checkers for [moleculer-healthcheck-middleware](https://github.com/r2d2bzh/moleculer-healthcheck-middleware) for projects using [moleculer-db-adapter-mongo](https://github.com/moleculerjs/moleculer-db/tree/master/packages/moleculer-db-adapter-mongo).


## Usage

This project gives createChecker functions to use with [moleculer-healthcheck-middleware](https://github.com/r2d2bzh/moleculer-healthcheck-middleware).

**Initialize the Mongo Liveness check**

```js
const HealthMiddleware = require('@r2d2bzh/moleculer-healthcheck-middleware');
const MongoHealthcheck = require('@r2d2bzh/moleculer-mongo-healthcheck');

const broker = new ServiceBroker({
  middlewares: [
    middlewares: [HealthMiddleware({
      liveness: {
        createChecker: MongoHealthcheck.createLivenessChecker
      }
    })],
  ],
});
```