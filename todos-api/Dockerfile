FROM node:16-alpine

WORKDIR /app

# Copy package.json and package-lock.json first for better caching
COPY package*.json ./

RUN npm install

# Copy application code
COPY . .

# Expose port
EXPOSE 8082

CMD ["node", "server.js"]