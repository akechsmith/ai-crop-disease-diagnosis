# Dockerfile.website
FROM nginx:alpine

# Copy static website content into NGINX html directory
COPY website/ /usr/share/nginx/html/

# Expose port 80
EXPOSE 80

# Start NGINX
CMD ["nginx", "-g", "daemon off;"]
