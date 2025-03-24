# Use the official Node.js 20 image as the base image
FROM node:20
# Set the working directory in the container(linux)
WORKDIR /app
# Install Newman and required reporters
RUN npm install -g newman newman-reporter-html newman-reporter-htmlextra
# Copy your Postman collection, environment, and data files
COPY DataDrivenAPI.json .
COPY GoRestEnvironment.json .
COPY myuser.csv .

# Set the command to run Newman with data-driven testing
CMD ["newman", "run", "DataDrivenAPI.json", "-e", "GoRestEnvironment.json", "-d", "myuser.csv", "-r", "cli,json,html,htmlextra"] 
