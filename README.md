# Complete Free Coding Bootcamp with the MERN Stack (beginner friendly) 

This is a series video and we are going to build a full-stack application from scratch using the MERN STACK (MongoDB, Express, React.js and Nodejs).

We will build a <strong>Sports Web App</strong> that allows you creating sports events and the app will include:

* User registration and authentication (maybe add facebook/gmail login if the series becomes popular) 
* Hashing password for security 
* Session control
* CRUD operations (create, read, update and delete) 
* Search for events using filters (Running, Cycling or Swimming) 
* Sign UP for event in order to participate
* Upload images to the server
* Website notification using web sockets (in order to approve or refuse the Event Sign UP request) 


## Fix required for episode 10
It is natural that after some time and a few updates, something breaks because many people forget to install the same dependencies versions that I have used when recorded the Bootcamp.
So I have decided to update socket.io and socket.io-client to the latest version (3.1.1).

That will fix the cors issue that many of you face and prevent the Bootcamp from being outdated.

please check the code for the [server](https://github.com/LionelPerrault/mern-course-bootcamp/blob/master/episode-10-Add-websockets-and-fix-Register/backend/src/server.js) and the [client](https://github.com/LionelPerrault/mern-course-bootcamp/blob/master/episode-10-Add-websockets-and-fix-Register/fronted/src/pages/Dashboard/index.js).

on the server-side please update the server.js to the following code.

```js
const server = http.Server(app)
const io = require("socket.io")(server, {
	cors: {
		origin: "*",
		methods: ["GET", "POST", "DELETE"]
	}
});

```

on the client side please update the Dashboard page with the following code.

```js
    const socket = useMemo(
        () =>
            socketio.connect('http://localhost:8000/', { query: { user: user_id } }),
        [user_id]
    );
```
## Deploying your webapp

For deploying this project we will modificate our backend and start using the S3 data storage from AWS.
Heroku does not keep your files into the server and because of that we are moving away from saving the images in disk to saving the images into the S3 that will host the images for us.
You will need to create an AWS account and a new bucket that will be explained into the Episode 13-A.
Following the next episode 13-B we are spliting the Backend and Frontend into two separeted projects to take the advantage of Heroku's CI/CD that basically deploys your code automatically when it detects a new code into your github repository.

# React Native Bootcamp 2021

The React Native Bootcamp is out we will build a client for the Web-App we built here, please find more about it [here](https://github.com/LionelPerrault/react-native-bootcamp)

## Fancy support my work so I can do more of it?
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate?hosted_button_id=YT9MSXE2JBK46)

## Want to know more about my motivation for this project?
[Read my blog post](http://italktech.io/mern-coding-bootcamp/)
