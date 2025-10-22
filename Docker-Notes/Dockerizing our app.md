`Dockerizing` your app, which means putting your application inside a Docker container so it can run anywhere reliably.
## Create a `Dockerfile`

A `**Dockerfile** `is a blueprint for building a Docker image of your app.

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