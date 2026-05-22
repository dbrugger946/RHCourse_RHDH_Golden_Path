FROM registry.redhat.io/ubi9/nodejs-22:latest
WORKDIR /app
USER root

# Copy the folder containing the React app
COPY ./react-app-frontend ./

RUN chgrp -R 0 /app && \
    chmod -R g=u /app
USER 1001:0

# Install dependencies
RUN npm install

# Verify installed packages and directory content
RUN ls -la /app

# Build the React app for production
RUN npm run build

# Expose the port and start the app
EXPOSE 3000
CMD ["npm", "start"]

