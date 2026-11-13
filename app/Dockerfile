# Testable Nginx image for the CI smoke test.
FROM nginx:1.28-alpine
COPY nginx.conf /etc/nginx/nginx.conf
RUN mkdir -p /var/log/securelab && nginx -t
EXPOSE 80
