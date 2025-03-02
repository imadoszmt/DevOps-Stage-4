# Use Node.js as a base image
FROM node:14 as build-stage

# Set working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy project files and build
COPY . .
RUN npm run build

EXPOSE 8080
CMD ["npm", "run", "serve"]