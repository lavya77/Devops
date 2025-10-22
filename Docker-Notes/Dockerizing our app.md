`Dockerizing` your app, which means putting your application inside a Docker container so it can run anywhere reliably.
## Create a `Dockerfile`

A `**Dockerfile`** `is a blueprint for building a Docker image of your app.

**Example: `Node.js` App**

```
# Use official Node.js image
FROM node:18

# Set working directory inside container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all app files
COPY . .

# Expose port the app listens on
EXPOSE 3000

# Start the app
CMD ["node", "index.js"]

```
known as base image.

## Building Docker Image
```
docker build -t myapp:1.0 .
```
- `-t myapp:1.0` → name & tag of the image
    
- `.` → current directory (where `Dockerfile` is)
## Run Container

```
docker run myapp:1.0
```

```
docker run-it myapp:1.0 bash
```

TO run all the multiple images we created we use docker compose,

```
docker-compose up -d
```

