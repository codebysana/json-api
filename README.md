# JSON API – Simple Backend with JSON Server

This project is a minimal Node.js application that serves data from a JSON file using [JSON Server](https://github.com/typicode/json-server).  
It was built to provide a quick, mock backend API for testing and demonstration purposes.

---

## Project Overview
I created this repository to simulate a real API without the complexity of setting up a full backend stack.  
Using JSON Server, I could quickly define endpoints, serve data, and make it accessible for front-end development or prototyping.

---

## Technologies Used
- **Node.js** – JavaScript runtime environment
- **JSON Server** – Mock REST API generator
- **JavaScript (ES6)** – Core language for backend scripting
- **Vercel** – Hosting & deployment platform
- **npm** – Dependency management

---

## Steps I Performed in This Project

## 1. **Initialized the Node.js Project**
- Created a new project directory and ran:
  ```bash
  npm init -y
* This generated the package.json file to manage dependencies.```

## 2. Installed JSON Server
Added JSON Server as a dependency:
````
npm install json-server
````
* This package allows serving a JSON file as a fully functional REST API.

## 3. Created the Database File
Added a db.json file containing data in JSON format.

Structured the data into collections (e.g., users, posts, products) so JSON Server could automatically create RESTful endpoints.

Example snippet from db.json:
````
{
  "users": [
    { "id": 1, "name": "Jane Doe" },
    { "id": 2, "name": "John Smith" }
  ]
}
````
## 4. Built the Server Script

* Created index.js to configure and start the JSON Server.
* Imported JSON Server, set up middleware, and pointed it to db.json.
* Configured the server to listen on a specific port (default: 3000).

Example:
````
const jsonServer = require('json-server');
const server = jsonServer.create();
const router = jsonServer.router('db.json');
const middlewares = jsonServer.defaults();

server.use(middlewares);
server.use(router);
server.listen(3000, () => {
  console.log('JSON Server is running');
});
````
## 5. Tested the API Locally
Ran the server with:
````
node index.js
````

Verified endpoints in the browser or Postman:

GET /users
GET /users/id
POST /users

## 6. Deployed to Vercel
Linked the GitHub repository to Vercel.

Configured the project with:

* Build Command: ````npm install````
* Start Command: ````node index.js````

Deployed successfully, making the API publicly accessible via a live Vercel URL.


