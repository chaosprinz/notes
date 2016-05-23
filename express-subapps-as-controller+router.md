Man kann in Express, ganz ähnlich wie rubys sinatra, diverse Express-apps definieren und diese als router nutzen.

Gehen wir von folgender ```index.js``` aus:

```javascript
var app = require('express')()
var http = require('http').Server(app)
var path = require('path')

var routesDir = path.join(__dirname, 'routes')
//mounten von ./routes/post.js auf /post
App.use('/post', require(path.join(routesDir, 'post'))
//mounten von ./routes/main.js auf /
App.use('/', require(path.join(routesDir, 'main'))

http.listen(3000, function () {
  console.log("listening on *:3000")
})
```

Wir benötigen nun also noch den Ordner ```routes``` mit den beiden Dateien ```post.js``` und ```main.js```.

```javascript
// ./routes/post.js
var app = require('express')()
app.get('/', function(req, res) {
  res.send("Das ist die post-seite")
}
module.exports = app

// ./routes/main.js
var app = require('express')()
app.get('/', function(req, res) {
  res.send("Das ist die start-seite")
}
module.exports = app
```

Auf diese Weise lassen sich Express-Applikation wundervoll modulariesieren. Der Vorteil dieser Methode gegenüber Express.Router ist, dass die Router so ihre eigenen Settings haben können.