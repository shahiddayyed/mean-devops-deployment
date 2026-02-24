# Useing official Node image
FROM node:18-alpine

# Set working directory inside container
WORKDIR /app

# Copy package files first (for better caching)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy remaining project files
COPY . .

# Expose backend port
EXPOSE 8080

# Start the application
CMD ["node", "server.js"]