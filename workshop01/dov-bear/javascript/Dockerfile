FROM node:22-bullseye 

## Build the app
# Create app directory and CD into it
WORKDIR /app

# Inside app directory
# Copy all source code to the image
# relative to the Dockerfile
COPY package.json .
COPY package-lock.json .
COPY main.js .
COPY public public
COPY views views

# Install dependencies
RUN npm ci

## Run the app
# Environment variables used by app (to tell people what can be configred)
ENV PORT=5000
ENV INSTANCE_NAME=workshop01
ENV INSTANCE_HASH=xyz

# Expose the port the app runs on
EXPOSE $PORT

# Run the app
ENTRYPOINT node main.js