FROM nginx:latest
# FROM nginx:alpine

# Remove default configuration if needed
RUN rm /etc/nginx/conf.d/default.conf

# Remove default config if needed and copy layer 4 configuration
COPY nginx.conf /etc/nginx/nginx.conf

# Expose your Layer 4 port
EXPOSE 80
# EXPOSE 12345/tcp
# EXPOSE 12345/udp

# Run NGINX in the foreground so Docker can track the process properly
CMD ["nginx", "-g", "daemon off;"]
