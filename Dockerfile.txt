# Use Node.js as the base image
FROM node:14

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json into the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the entire application code into the container
COPY . .

# Expose port 3000 (or the port your application uses)
EXPOSE 3000

# Set the command to run your application
CMD ["npm", "start"]