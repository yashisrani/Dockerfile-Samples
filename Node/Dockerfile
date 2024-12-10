# Use a Node.js base image
FROM node:16-alpine

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy application code
COPY . .

# Run the Node.js application
CMD ["node", "index.js"]

# Expose the port
EXPOSE 3000
