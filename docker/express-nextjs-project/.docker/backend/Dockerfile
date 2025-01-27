# Use an official Node.js image
FROM node:18

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the app's source code
COPY . .

# Build the TypeScript code
RUN npm run build

# Expose the port the app listens on
EXPOSE 5000

# Start the app
CMD ["npm", "start"]
