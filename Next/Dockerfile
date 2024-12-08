# Use a Node.js base image
FROM node:16-alpine

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy application code
COPY . .

# Build the Next.js application
RUN npm run build

# Start the Next.js application
CMD ["npm", "start"]

# Expose the port
EXPOSE 3000
