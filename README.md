# Custom URL Shortener

This project is a custom URL shortener built using Node.js and MongoDB. It allows users to shorten long URLs into more manageable and shareable links.

## What is a URL Shortener?

A URL shortener is a tool that takes a long URL and generates a shorter, more compact version. These shortened URLs are easier to share, especially in contexts where character count is limited, such as social media platforms or text messages.

## Functionality

The project provides the following functionalities:

- `POST /URL`: Generates a new short URL and returns the shortened URL in the format example.com/random-id.
- `GET /:id`: Redirects the user to the original URL associated with the provided ID.
- `GET /URL/analytics/:id`: Returns the number of clicks for the provided short ID.

## Controller: Handles URL Shortening Logic

The `controller/` folder contains files that handle the logic for different aspects of the URL shortening functionality.

### url.js

In the `controller/` folder, the `url.js` file is like the brain behind creating short links. When you want to make a long link shorter, this file does the magic. It takes the long link you give it, makes a short, unique code for it, and saves it so you can use it later. It's like a manager that handles all the work of making short links for you.

## Model: Manages Shortened URL Data

The `models/` folder contains files that help manage the data for the shortened URLs.

### url.js

The `url.js` file inside the `models/` folder acts like a digital notebook. It keeps track of all the short links we create. Each entry in this notebook includes:
- **Short ID**: A unique code for the short link.
- **Original URL**: The long link that we want to make shorter.
- **Visit History**: A record of when people click on the short link.

Whenever we create a new short link, this file makes sure to save it in our digital notebook so we can find it later. It's like a librarian who organizes all our short links for us.

## Model: Handles URL Generation Requests

The `models/` folder contains files that handle requests related to creating new short URLs.

### url.js

The `url.js` file inside the `models/` folder is like a guidebook for processing requests to create new short URLs. It sets up rules for how these requests should be handled.

Imagine you're in charge of managing a queue at a ticket counter. This file is like the guidebook that tells your team how to process customers who want to buy tickets. It provides instructions on what to do when a customer asks for a ticket.

Here's what's happening in this file:
- It uses a special tool called Express to create a set of rules for handling requests.
- It tells Express that when it receives a specific type of request (called a POST request) at a certain address (called "/"), it should call a function called `handleGenerateNewShortURL`.
- Finally, it exports these rules so that they can be used by other parts of the application.

In simpler terms, this file is setting up the system to handle requests from users who want to create new short URLs. It's like creating a plan for how to process those requests and telling the computer how to follow that plan.

## Database Connection: Connects to MongoDB

The `connect.js` file is responsible for connecting our application to a MongoDB database. It sets up the connection so that our application can store and retrieve data from the database.

Imagine your application as a house, and the MongoDB database as a storage unit where you keep all your important stuff. This file is like the key that allows your application to open the door and access the storage unit.

Here's what's happening in this file:
- It uses a tool called Mongoose to help connect our application to the MongoDB database.
- It defines a function called `connectToMongoDB` that takes a URL (address) of the MongoDB database as input.
- Inside this function, it connects to the MongoDB database using the provided URL.

In simpler terms, this file ensures that our application can communicate with the MongoDB database and access the data stored there. It's like setting up the connection between your application and the place where it stores its data.

## Server Setup and Routing: Handles Requests

The `index.js` file serves as the main control center of our custom URL shortener application. It sets up the server, defines routes for handling different types of requests, and connects to the MongoDB database.

Imagine this file as the manager of a store. It opens the doors, welcomes customers, guides them to the right sections, and keeps track of everything happening in the store.

Here's what's happening in this file:
- It uses a tool called Express to create a web server for our application.
- It imports functions and modules from other files to handle database connection (`connectToMongoDB`), define routes (`urlRoute`), and interact with the MongoDB database (`URL` model).
- It starts by connecting to the MongoDB database using the `connectToMongoDB` function.
- It sets up the server to parse JSON data using `express.json()` so that it can understand requests with JSON payloads.
- It defines a route for handling URL shortening requests (`/url`) using the `urlRoute`.
- It defines a route for redirecting users based on the short ID provided in the URL. It looks up the original URL associated with the short ID in the database and redirects the user accordingly.
- Finally, it starts the server and listens for incoming requests on a specified port.

In simpler terms, this file is like the manager of our application, coordinating all the different parts to ensure that everything runs smoothly. It handles incoming requests, interacts with the database, and directs traffic to the appropriate places.




## Requirements

To run this project, you need the following:

- Node.js (version 12 or higher)
- MongoDB database


## Installation

To install and run this project, you need to have Node.js and npm (Node Package Manager) installed on your system.

### Step 1: Initialize the Project

First, initialize your project by running:

```bash
npm init -y

npm install express shortid nodemon

