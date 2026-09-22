FROM nginx:latest
# FROM nginx:alpine

# Remove default configuration if needed
RUN rm /etc/nginx/conf.d/default.conf

# Copy the Layer 7 HTTP configuration
COPY nginx.conf /etc/nginx/nginx.conf

# Expose the HTTP port
EXPOSE 80
# Expose the TCP port
EXPOSE 3304

# EXPOSE 12345/tcp
# EXPOSE 12345/udp

# Run NGINX in the foreground so Docker can track the process properly
CMD ["nginx", "-g", "daemon off;"]
