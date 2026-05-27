FROM registry.redhat.io/ubi9/nodejs-22:latest

USER root

# Copy the folder containing the React app
COPY ./react-app-frontend ./

# Install dependencies
RUN npm install


RUN chgrp -R 0 /opt/app-root/src && \
    chmod -R g=u /opt/app-root/src

RUN chown -R 1001:0 /opt/app-root/src 
USER 1001


# Build the React app for production
# RUN npm run build

# Expose the port and start the app
EXPOSE 3000
CMD ["npm", "start"]