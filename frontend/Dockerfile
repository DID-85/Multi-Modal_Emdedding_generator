# Use Node.js as base image
FROM node:18

# Set working directory
WORKDIR /frontend

# Copy package.json and package-lock.json for caching
COPY template/package.json template/package-lock.json ./

# Install dependencies
RUN npm install

# Copy the entire frontend project
COPY template ./

# Ensure `lucide-react` is installed
RUN npm install lucide-react --save

# Build Remix app
RUN npm run build

# Expose Remix's default port
EXPOSE 3000

# Start the Remix app
CMD ["npm", "run", "start"]
