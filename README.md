# MEAN Stack Front To Back
####

- [x] Step 1 : 
- [x] [Step 2 : Express Setup & Routes](https://www.youtube.com/watch?v=DQ9pZ2NKXRo&t=85s)
	- [x] Commit 1 : Setup Application
	- [x] Commit 2 : Create Register Route
	- [x] Commit 3 : Create Authenticate, Profile, Validate Routes
	- [x] Commit 4 : Set Static Folder, Create Public Folder
	- [x] Commit 5 : Connect To MongoDB
- [x] [Step 3 : User Model & Register](https://www.youtube.com/watch?v=1ZeDy2QI3OE)
	- [x] Commit 6 : Create User Schema (Uers Model)
	- [x] Commit 7 : Register user by Postman
- [] [Step 4 : API Authentication and Token](https://www.youtube.com/watch?v=6pdFXmTfkeE)

## Step 1 :
## Step 2 :
### [Express Setup & Routes](https://www.youtube.com/
watch?v=DQ9pZ2NKXRo&t=85s)
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

## Step 2 :
### [Step 3 : User Model & Register](https://www.youtube.com/watch?v=1ZeDy2QI3OE)
#### Commit 6 :
##### Source :
- [bcryptjs](https://www.npmjs.com/package/bcryptjs)

#### Commit 7 : 
- [Postman](chrome://apps)
	- POST
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
#### Mongo
```
$ mongo
> show dbs
> use meanauthapp
> show collections
> db.users.find().pretty()
```