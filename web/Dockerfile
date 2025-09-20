# Use the official NGINX base image
FROM nginx
# Remove the default index.html if it exists
RUN rm -rf /usr/share/nginx/html/index.html 
# Remove the default NGINX configuration files
RUN rm -rf /etc/nginx/nginx.conf
RUN rm -rf /etc/nginx/conf.d/default.conf
# Copy your custom NGINX configuration
COPY default.conf /etc/nginx/conf.d/default.conf  # Use conf.d instead of nginx.conf
# Copy static files to the NGINX HTML folder
COPY static /usr/share/nginx/html 
# Set environment variable for upstream hosts (no spaces around '=')
ENV CATALOGUE_HOST="catalogue"
# Ensure that NGINX runs in the foreground
CMD ["nginx", "-g", "daemon off;"]