# Taskie monorepo
This repo contains source code for both backend and frontend of the Taskie app.

## Install
To install dependencie for both backend and frontend, run:
```bash
yarn install
```

## Run
### Run backend and frontend simultaneously:
```bash
yarn dev
```
Backend will be up and running at localhost:4000
Frontend will be up and running at localhost:3000

### Run backend and front end indepently:
To run backend:
```bash
yarn backend
```
To run frontend:
```bash
yarn frontend
```

## Deployment
Frontend is deployed at [](https://taskie-frontend.vercel.app)
Backend is deployed at [](https://taskie-v9gb.onrender.com)
CD has been setup so that each commit or merge to the `main` branch will trigger a job at the appropriate platform.

## Backend
Username and password are stored as environemnt variables on Render.

In local development, create your own `.env` file, copy content from `.example.env` and replace `username`, `password` with valid values.

Connect to MongoDB
```js
const { MongoClient, ServerApiVersion } = require('mongodb');
const uri = "mongodb+srv://dev:<password>@cluster0.vtzci3q.mongodb.net/?retryWrites=true&w=majority";

// Create a MongoClient with a MongoClientOptions object to set the Stable API version
const client = new MongoClient(uri, {
  serverApi: {
    version: ServerApiVersion.v1,
    strict: true,
    deprecationErrors: true,
  }
});

async function run() {
  try {
    // Connect the client to the server	(optional starting in v4.7)
    await client.connect();
    // Send a ping to confirm a successful connection
    await client.db("admin").command({ ping: 1 });
    console.log("Pinged your deployment. You successfully connected to MongoDB!");
  } finally {
    // Ensures that the client will close when you finish/error
    await client.close();
  }
}
run().catch(console.dir);
```