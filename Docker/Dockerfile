# Use official Node.js 18 base image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy only dependency files first (for better caching)
COPY package.json yarn.lock ./

# Install dependencies
RUN yarn install --frozen-lockfile

# Copy the rest of your application
COPY . .

# Build the app
RUN yarn build

# Expose port 9000
EXPOSE 9000

# Start the app
CMD ["yarn", "start"]
