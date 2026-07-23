FROM nginx:1.27-alpine

# Remove default nginx welcome page
RUN rm -rf /usr/share/nginx/html/*

# Copy the static site
COPY index.html /usr/share/nginx/html/index.html

# nginx image scans on port 80 by default
EXPOSE 80

HEALTHCHECK --interval=30s --timeout=3s CMD wget -qO- http://localhost/ || exit 1

CMD ["nginx", "-g", "daemon off;"]
