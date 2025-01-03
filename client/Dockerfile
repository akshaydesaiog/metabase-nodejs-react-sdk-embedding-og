# Base image for the client
FROM node:18

# Set working directory for the client
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Install env-cmd globally
RUN npm install -g env-cmd

# Copy the rest of the application files
COPY . .

# Expose the client port (3100)
EXPOSE 3100

# Start the client with env-cmd on port 3100
CMD ["env-cmd", "-f", ".env", "npm", "start"]
