# Use official Nginx image as base
FROM nginx:alpine

# Set working directory inside container
WORKDIR /usr/share/nginx/html

# Remove default nginx static assets
RUN rm -rf ./*

# Copy your static files (HTML, CSS, JS) into the container
COPY . .

# Expose port 80
EXPOSE 80

# Nginx will automatically serve index.html
CMD ["nginx", "-g", "daemon off;"]
