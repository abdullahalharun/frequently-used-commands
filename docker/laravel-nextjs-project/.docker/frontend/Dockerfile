# Use the official Node.js image as the base image
FROM node:18-alpine

# Set the working directory
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json files
COPY ../../itqaan-next-frontend/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY ../../itqaan-next-frontend .

# Expose the port the app runs on
EXPOSE 3000

# Start the application
CMD ["npm", "run", "dev"]