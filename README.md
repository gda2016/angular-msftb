# MEAN Stack Front To Back
####

- [x] Step 1 : 
- [x] [Step 2 : Express Setup & Routes](https://www.youtube.com/watch?v=DQ9pZ2NKXRo&t=85s)
	- [x] Commit  1 : Setup Application
	- [x] Commit  2 : Create Register Route
	- [x] Commit  3 : Create Authenticate, Profile, Validate Routes
	- [x] Commit  4 : Set Static Folder, Create Public Folder
	- [x] Commit  5 : Connect To MongoDB
- [x] [Step 3 : User Model & Register](https://www.youtube.com/watch?v=1ZeDy2QI3OE)
	- [x] Commit  6 : Create User Schema (Uers Model)
	- [x] Commit  7 : Register user by Postman
- [x] [Step 4 : API Authentication and Token](https://www.youtube.com/watch?v=6pdFXmTfkeE)
	- [x] Commit  8 : Export Passport module
	- [x] Commit 10 : Setup Route post authenticate
	- [x] Commit 11 : Exports comparePassword function to models user.js
	- [x] Commit 12 : Make a POST request by Postman
	- [x] Commit 13 : Make Prifile protected in route/users.js and GET user profile
- [x] [Step 5 : Angular 2 Components & Routes](https://www.youtube.com/watch?v=zrViDpWiNVE&t=21s)
	- [x] Commit 14 : Prepaer Client installation
	- [x] Commit 15 : Install Angular Client & and Create Components
	- [x] Commit 16 : Create a Routers
	- [x] Commit 17 : Create Navbar by Bootstrap
- [x] [Step 6 : Register Component, Validation & Flash Messages](https://www.youtube.com/watch?v=bxZAPoeMr7U)
	- [x] Commit 18 : Create Home Jumbotron and three column
	- [x] Commit 19 : Connect Register Component
	- [x] Commit 20 : Validation, Create Services
	- [ ] Commit 21 : Flash Messages

## Part 1 : [GitHub](https://github.com/bradtraversy/nodeauthapp)
## Step 1 :
## Step 2 :
### [Express Setup & Routes](https://www.youtube.com/watch?v=DQ9pZ2NKXRo&t=85s)
#### Commit 1 :
```
$ mkdir meanauthapp
$ cd meanauthapp

$ git init
$ touch README.md
$ git checkout -b step_2
$ git branch
$ git add --all
$ git commit -m "first commit"
$ git remote add origin https://github.com/gda2016/
$ git push -u origin step_2
 
$ npm init
$ npm install
$ sudo npm install -g nodemon
$ nodemon
```

#### Commit 2 : 
##### Source :
- [CORS on ExpressJS](https://enable-cors.org/server_expressjs.html)
- [cors npm](https://www.npmjs.com/package/cors)

#### Commit 5 :
##### Source :
- [How to Install MongoDB on CentOS 7](https://www.liquidweb.com/kb/how-to-install-mongodb-on-centos-7/)
```
$ sudo systemctl status mongod
$ sudo systemctl start mongod
$ sudo lsof -iTCP -sTCP:LISTEN | grep mongo
$ mongostat 
```
##### Create MongoDB
```
$ mongo
> show dbs
> use meanauthapp
> db.users.save( {username: "gda"} )
> db.users.find()
```

## Step 3 :
### [User Model & Register](https://www.youtube.com/watch?v=1ZeDy2QI3OE)
#### Commit 6 :
##### Source :
- [bcryptjs](https://www.npmjs.com/package/bcryptjs)

#### Commit 7 : 
##### Postman chrome://apps
	- POST
	- http://localhost:3000/users/register
	- Headers
	- Key : Content-type
	- Value : application/json
	- Body : 
	```
	{
	"name":"John Doe",
	"email":"john@gmail.com",
	"username":"john",
	"password":"123456"
	}
	```
	- Send
##### Mongo
```
$ mongo
> show dbs
> use meanauthapp
> show collections
> db.users.find().pretty()
```

## Step 4 : 
### [Step 4 : API Authentication and Token](https://www.youtube.com/watch?v=6pdFXmTfkeE)
#### Commit 8 :
##### Source :
 - [passport-jwt](https://www.npmjs.com/package/passport-jwt)

#### Commit 12 :
##### Postman chrome://apps
	- POST
	- http://localhost:3000/users/authenticate
	- Headers
	- Key : Content-type
	- Value : application/json
	- Body : 
	```
	{
	"username":"john",
	"password":"123456"
	}
	```
	- Send

#### Commit 13 :
##### Postman chrome://apps
	- POST
	- http://localhost:3000/users/profile
	- Key : Authorization
	- Value : insert hash from previous POST
	```
	JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyIkX18iOnsic3RyaWN0TW9kZSI6dHJ1ZSwic2VsZWN0ZWQiOnt9LCJnZXR0ZXJzIjp7fSwiX2lkIjoiNTk1M2I0YTk2MGRmODMzNDZlMWU0MjVmIiwid2FzUG9wdWxhdGVkIjpmYWxzZSwiYWN0aXZlUGF0aHMiOnsicGF0aHMiOnsicGFzc3dvcmQiOiJpbml0IiwidXNlcm5hbWUiOiJpbml0IiwiZW1haWwiOiJpbml0IiwiX192IjoiaW5pdCIsIm5hbWUiOiJpbml0IiwiX2lkIjoiaW5pdCJ9LCJzdGF0ZXMiOnsiaWdub3JlIjp7fSwiZGVmYXVsdCI6e30sImluaXQiOnsiX192Ijp0cnVlLCJwYXNzd29yZCI6dHJ1ZSwidXNlcm5hbWUiOnRydWUsImVtYWlsIjp0cnVlLCJuYW1lIjp0cnVlLCJfaWQiOnRydWV9LCJtb2RpZnkiOnt9LCJyZXF1aXJlIjp7fX0sInN0YXRlTmFtZXMiOlsicmVxdWlyZSIsIm1vZGlmeSIsImluaXQiLCJkZWZhdWx0IiwiaWdub3JlIl19LCJwYXRoc1RvU2NvcGVzIjp7fSwiZW1pdHRlciI6eyJkb21haW4iOm51bGwsIl9ldmVudHMiOnt9LCJfZXZlbnRzQ291bnQiOjAsIl9tYXhMaXN0ZW5lcnMiOjB9fSwiaXNOZXciOmZhbHNlLCJfZG9jIjp7Il9fdiI6MCwicGFzc3dvcmQiOiIkMmEkMTAkdVQ2QWY1dmxab2ROU3NsR3M0MTJDdUphZE5XcUtDcWJGMHhmM2hVeXd6UWh2SVFVaTZHTWkiLCJ1c2VybmFtZSI6ImpvaG4iLCJlbWFpbCI6ImpvaG5AZ21haWwuY29tIiwibmFtZSI6IkpvaG4gRG9lIiwiX2lkIjoiNTk1M2I0YTk2MGRmODMzNDZlMWU0MjVmIn0sIiRpbml0Ijp0cnVlLCJpYXQiOjE0OTg3MDM2NTQsImV4cCI6MTQ5OTMwODQ1NH0.j6DzEmF5wNVe3MkfyAMGkk9SQmhyGvRxPwztsNmfgX4
	```
	- Send

## Step 5 : 
### [Step 5 : Angular 2 Components & Routes](https://www.youtube.com/watch?v=zrViDpWiNVE&t=21s)
#### Commit 14 :
##### Prepaer Client installation
#### Commit 15 :
##### Install angular Client
###### Server
```
$ cd /app/webapps/ng/meanauthapp/
$ sudo npm install -g angular-cli
$ ng new client
/*
 angular-cli.json
 "outDir": "../public",
 */
$ nodemon
```
###### Client [Angular-cli](https://github.com/angular/angular-cli)
```
$ cd /app/webapps/ng/meanauthapp/client
$ ng serve
// http://localhost:4200/
$ mkdir -p src/app/components && cd src/app/components
$ ng g component navbar
// Check component navbar
// app.component.html >> <app-navbar></app-navbar>
$ ng serve
$ ng g component login
$ ng g component register
$ ng g component home
$ ng g component dashboard
$ ng g component profile
$ ng serve
```

#### Commit 16 :
##### Create a Router
###### [bootswatch](https://bootswatch.com/) Sandstone -> Download

#### Commit 17 :
##### Create Navbar by Bootstrap
###### [bootstrap](http://getbootstrap.com/getting-started/#examples) Get started-> Examples -> Bootstrap simple template

## Step 6 : 
###
#### Commit 19 : Connect Register Component
##### Check function onRegisterSubmit
```
// in register.component.ts
	onRegisterSubmit() {
		console.log(this.name);
	}
```

#### Commit 20 : Validation, Create Services
##### Create Services
```
$ cd ..
$ mkdir services && cd Services
$ ng g service validate
```
##### [JavaScript Validate Email REGX](https://stackoverflow.com/questions/46155/how-to-validate-email-address-in-javascript)
```
function validateEmail(email) {
    var re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(email);
}
```
##### Check Validation
```
$ cd /app/webapps/ng/meanauthapp/client
$ ng serve
```


Angular is running in the development mode. Call enableProdMode() to enable the production mode.

https://bootswatch.com/