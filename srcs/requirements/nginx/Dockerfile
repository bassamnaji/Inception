FROM debian:latest

# Install dependencies
RUN apt-get update && apt-get install -y \
    nginx
    # curl

# Copy the NGINX configuration
COPY conf /etc/nginx/sites-enabled/default

COPY ssl/certificate.pem /etc/ssl/certs/certificate.pem
COPY ssl/key.pem /etc/ssl/private/key.pem
# Copy the default site configuration
# COPY default.conf /etc/nginx/conf.d/default.conf

# Copy the content for the default site
# COPY html/ /var/www/html/

# Expose port 80 and run NGINX as a non-root user
EXPOSE 80 443
# USER nginx
CMD ["nginx", "-g", "daemon off;"]