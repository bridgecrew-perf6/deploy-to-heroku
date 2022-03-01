1. Started a blank new ionic app using
    --> ionic start 

2. Install express module and path in our project
    --> npm install express path --save

3. setup git repositry

4. configure of package.json file

    dependencies 
        "@angular/compiler": "~13.0.0",
        "@angular/compiler-cli": "~13.0.0",
        "typescript": "~4.4.4"

    "scripts": {
        "start": "node server.js",
        "build": "ng build",
        "heroku-postbuild": "ng build",
    },

    "engines": { 
        "node": "16.13.1",
        "npm": "8.1.2"
    },

5. create a Server.js file in the root depositry of our app

    const express = require('express');
    const { Server } = require('http')
    const path = require('path');
    const app = express();
    app.use(express.static(__dirname + '/www/'));
    app.get('/*', function(req,res) {
    res.sendFile(path.join(__dirname+
    '/www/index.html'));});
    app.listen(process.env.PORT || 8080);

6. setup heroku and lauch our project