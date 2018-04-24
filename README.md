var cluster = require('cluster');
var amount = 20;

if (cluster.isMaster) {

    for (var i = 0; i < amount; i += 1) {
        cluster.fork();
    }

    cluster.on('exit', function () {
        cluster.fork();
    });

} else {
    require('./index');
}

var game_pin = {7084484

}

{
  "name": "kahoot-bot",
  "version": "0.0.1",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Yannick Forget",
  "license": "ISC",
  "dependencies": {
    "kahoot.js": "^1.0.0",
    "nodejs-randomnames": "^1.0.1",
    "prompt": "^1.0.0",
    "readline": "^1.3.0"
  }
}

var Kahoot = require('kahoot.js');
var client = new Kahoot;
var NameGenerator = require('nodejs-randomnames');
var randomName = NameGenerator.getRandomName();
var game_pin = 6039738;
var randomnumber = Math.round(Math.random() * 3);

console.log("Joining kahoot...  ");
client.join(game_pin, randomName);
client.on("joined", () => {
    console.log("I joined the Kahoot!");
});
client.on("questionStart", question => {
    console.log("A new question has started, answering the first answer.");
    question.answer(randomnumber);
    randomnumber = Math.floor(Math.random() * 3);
});
client.on("quizEnd", () => {
    console.log("The quiz has ended.");
});



