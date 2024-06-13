# Use an official Node.js 14 as a parent image
FROM node:14-slim

# Set the working directory inside the container to /usr/src/app
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json (if available)
# This is done before installing dependencies to leverage Docker cache
COPY package.json package-lock.json* ./

# Install dependencies
# npm ci is used in place of npm install when you want to replicate a build (it's cleaner for production)
RUN npm ci --only=production

# Copy the rest of your application's source code into the container
COPY . .

# Expose the port your app runs on
EXPOSE 3000

# Command to run your application
# npm start typically starts a server, ensure your package.json has the right start script
CMD ["npm", "start"]
