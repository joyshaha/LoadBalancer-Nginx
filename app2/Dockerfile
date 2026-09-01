# Use the lightweight Nginx Alpine base image
FROM nginx:latest

RUN apt-get update && apt install net-tools -y

# Remove the default Nginx configuration file
# RUN rm /etc/nginx/conf.d/default.conf

# Copy your custom Nginx configuration file
# COPY nginx.conf /etc/nginx/nginx.conf

# Copy your static HTML website files into the default web root
# Assumes your HTML files are in a local directory named './public'
COPY ./html /usr/share/nginx/html

# Expose port 80 to the outside world
EXPOSE 80

# Start Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]
