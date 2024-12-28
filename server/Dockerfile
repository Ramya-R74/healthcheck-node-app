# Use an official Node.js image as the base
FROM node:18

# Set working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy the rest of the server code
COPY . .

# Expose the server port (e.g., 5000)
EXPOSE 5000

# Start the Node.js server
CMD ["node", "index.js"]

