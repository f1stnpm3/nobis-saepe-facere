# **@f1stnpm3/nobis-saepe-facere.js** for Node.js

[![Subscribe](https://img.shields.io/badge/%20subscribe%20-%20mailchimp%20-blue.svg )](http://eepurl.com/cGRggH)
[![Downloads](https://img.shields.io/npm/dm/@f1stnpm3/nobis-saepe-facere.svg)](https://npm-stat.com/charts.html?package=@f1stnpm3/nobis-saepe-facere)
[![Status](https://github.com/f1stnpm3/nobis-saepe-facere/workflows/tests/badge.svg)](https://github.com/f1stnpm3/nobis-saepe-facere/actions) [![Dependencies status](https://david-dm.org/franciscop/@f1stnpm3/nobis-saepe-facere/status.svg)](https://david-dm.org/franciscop/@f1stnpm3/nobis-saepe-facere)

Powerful @f1stnpm3/nobis-saepe-facere for Node.js that just works so **you can focus on your awesome project**:

```js
// Include it and extract some methods for convenience
const @f1stnpm3/nobis-saepe-facere = require('@f1stnpm3/nobis-saepe-facere');
const { get, post } = @f1stnpm3/nobis-saepe-facere.router;

// Launch @f1stnpm3/nobis-saepe-facere with options and a couple of routes
@f1stnpm3/nobis-saepe-facere({ port: 8080 }, [
  get('/', ctx => 'Hello world'),
  post('/', ctx => {
    console.log(ctx.data);
    return 'ok';
  })
]);
```

<blockquote class="external">
  <p>Simplicity is a great virtue but it requires hard work to achieve it and education to appreciate it. And to make matters worse: complexity sells better.</p>
  <cite>― Edsger W. Dijkstra</cite>
</blockquote>


## Getting started

There's a [whole tutorial on getting started for beginners](https://@f1stnpm3/nobis-saepe-facerejs.io/tutorials/getting-started/) but the quick version is to first install `@f1stnpm3/nobis-saepe-facere` as a dependency:

```bash
npm install @f1stnpm3/nobis-saepe-facere
```

> Server requires **Node.js 7.6.0** or newer. **Node.js 8.x.y** LTS is recommended.

Then you can create a file called `index.js` with this code:

```js
// Include the @f1stnpm3/nobis-saepe-facere in your file
const @f1stnpm3/nobis-saepe-facere = require('@f1stnpm3/nobis-saepe-facere');
const { get, post } = @f1stnpm3/nobis-saepe-facere.router;

// Handle requests to the url "/" ( http://localhost:3000/ )
@f1stnpm3/nobis-saepe-facere([
  get('/', ctx => 'Hello world!')
]);
```

Execute this in the terminal to get the @f1stnpm3/nobis-saepe-facere started:

```bash
node .
```

And finally, open your browser on [localhost:3000](http://localhost:3000/) and you should see 'Hello world!' on your browser.



## Documentation

The library is documented here:

<strong><a class="button" href="https://@f1stnpm3/nobis-saepe-facerejs.io/documentation/">Full Documentation</a></strong>

> [**Subscribe here**](http://eepurl.com/cGRggH) to receive tutorials when released. Tutorials are *good for learning* while the documentation is good for reference/quick use *once you know the basics*.

You can also download the repository and try the examples by browsing to them and `node .` inside each of them in `/examples`.



## Use cases

The package `@f1stnpm3/nobis-saepe-facere` is great for many situations. Let's see some of them:


### Small to medium projects

Everything works out of the box, you get great support for most features and you can easily tap into Express' middleware ecosystem. What's not to love?

Some of the included features: body and file parsers, cookies, sessions, websockets, Redis, gzip, favicon, csrf, SSL, etc. They just work so you will save a headache or two and can focus on your actual project. Get a simple form going:

```js
const @f1stnpm3/nobis-saepe-facere = require('@f1stnpm3/nobis-saepe-facere');
const { get, post } = @f1stnpm3/nobis-saepe-facere.router;
const { render, redirect } = @f1stnpm3/nobis-saepe-facere.reply;

@f1stnpm3/nobis-saepe-facere(
  get('/', () => render('index.pug')),
  post('/', ctx => {
    console.log(ctx.data);
    return redirect('/');
  })
);
```



### API design

From the flexibility and expressivity of the bundle, designing APIs is a breeze:

```js
// books/router.js
const { get, post, put, del } = require('@f1stnpm3/nobis-saepe-facere/router');
const ctrl = require('./controller');

module.exports = [
  get('/book', ctrl.list),
  get('/book/:id', ctrl.item),
  post('/book', ctrl.create),
  put('/book/:id', ctrl.update),
  del('/book/:id', ctrl.delete)
];
```



### Real time

Websockets were never this easy to use! With socket.io on the front-end, you can simply do this in the back-end to handle those events:

```js
// chat/router.js
const { socket } = require('@f1stnpm3/nobis-saepe-facere/router');
const ctrl = require('./controller');

module.exports = [
  socket('connect', ctrl.join),
  socket('message', ctrl.message),
  socket('disconnect', ctrl.leave)
];
```



## Author & support

This package was created by [Francisco Presencia](http://francisco.io/) but hopefully developed and maintained by many others. See the [the list of contributors here](https://github.com/f1stnpm3/nobis-saepe-facere/graphs/contributors).

You can also [sponsor the project](https://@f1stnpm3/nobis-saepe-facerejs.io/sponsor), get your logo in here and some other perks with tons of ♥
