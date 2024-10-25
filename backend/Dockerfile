# Step 1: Use Node.js as the base image
FROM node:20

# Step 2: Set the working directory in the container
WORKDIR /app

# Step 3: Copy the backend package files
COPY package*.json ./

# Step 4: Install backend dependencies
RUN npm install

# Step 5: Copy the backend source code
COPY . .

# Step 6: Expose the backend port
EXPOSE 5001

# Step 7: Set environment variables for production
ENV NODE_ENV=production

# Step 8: Start the backend server
CMD ["npm", "start"]
