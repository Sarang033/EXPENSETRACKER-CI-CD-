# Step 1: Use Node.js as the base image to build the frontend
FROM node:20 as build

# Step 2: Set the working directory
WORKDIR /app

# Step 3: Copy the package files and install dependencies
COPY package*.json ./
RUN npm install

# Step 4: Copy the frontend source code and build the React app
COPY . .
RUN npm run build

# Step 5: Use Nginx as the base image to serve the frontend
FROM nginx:alpine

# Step 6: Copy the build files to Nginx's default directory
COPY --from=build /app/build /usr/share/nginx/html

# Step 7: Expose the port Nginx is using
EXPOSE 80

# Step 8: Start Nginx
CMD ["nginx", "-g", "daemon off;"]
