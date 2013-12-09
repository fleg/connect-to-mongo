# Connect MongoDB

connect-to-mongo is a MongoDB session store backed by [node-mongodb-native](https://github.com/mongodb/node-mongodb-native) >= 1.3. Requires mongodb >= `2.2.0` for ttl collections.

## Installation

```sh
  npm install connect-to-mongo
```

## Options

  - `db` mongodb-native database object or database name defaulting to "test"
  - `collection` MongoDB collection name defaulting to "sessions"
  - `host` MongoDB server hostname defaulting to "127.0.0.1"
  - `port` MongoDB server port defaulting to 27017
  - `ttl` MongoDB session TTL in milliseconds
  - `user` User for MongoDB
  - `password` Password for MongoDB authentication
  - `ssl` Use SSL to connect to MongoDB defaulting to false

## Usage

```js
var connect = require('connect'),
  MongoStore = require('connect-to-mongo')(connect),
  app = connect();

app.use(connect.session({
  store: new MongoStore(options), secret: 'keyboard cat'
}));
```

For using it with express just replace `connect` with `express` in the example above.

## License

  MIT
