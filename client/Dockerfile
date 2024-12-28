# Use an official Node.js image as the base
FROM node:18

# Set working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy the rest of the client code
COPY . .

# Build the React app for production
RUN npm run build

# Use an official Nginx image for serving static files
FROM nginx:alpine

# Copy built files to Nginx's default public directory
COPY --from=0 /app/dist /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]

