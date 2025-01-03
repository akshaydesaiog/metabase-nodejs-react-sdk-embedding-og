# Base image for the server
FROM node:18

# Set working directory for the server
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Install env-cmd globally
RUN npm install -g env-cmd

# Copy the rest of the application files, including .env
COPY . .

# Expose the server port
EXPOSE 9090

# Start the server with env-cmd
CMD ["env-cmd", "-f", ".env", "npm", "start"]

