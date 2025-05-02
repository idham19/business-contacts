# Use a specific Node version instead of 'latest'
FROM node:18-alpine

# Create and set working directory
WORKDIR /app

# Set proper permissions for node user
RUN mkdir -p /app && chown -R node:node /app
USER node

# Copy package files first for better caching
COPY --chown=node:node package*.json ./

# Install dependencies
RUN npm install

# Copy application files
COPY --chown=node:node . .

# Environment variables
ENV NODE_ENV=development
ENV PORT=3000

# Expose port
EXPOSE 3000

# Start command
CMD ["node", "server.js"]