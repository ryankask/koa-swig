# koa-swig

[Koa][] view render based on [Swig][].

### Usage

#### Install

```
npm install koa-swig
```

#### Example

```js
var koa = require('koa');
var render = require('koa-swig');
var app = koa();

render(app, {
  autoescape: true,
  cache: 'memory', // disable, set to false
  views: path.join(__dirname, 'views'),
  ext: 'html',
  locals: locals,
  filters: filters
});

app.use(function *() {
  yield this.render('index');
});

app.listen(2333);
```

#### Settings

* [swig options](http://paularmstrong.github.io/swig/docs/api/#SwigOpts)
  - autoescape
  - cache
  - locals

* filters: swig custon [filters](http://paularmstrong.github.io/swig/docs/extending/#filters)

* ext: default view extname

* views: view root directory

### Licences

MIT

[koa]: http://koajs.com
[swig]: http://paularmstrong.github.io/swig/
