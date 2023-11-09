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
