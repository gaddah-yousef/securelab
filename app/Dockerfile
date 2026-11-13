# Testable Nginx image for the CI smoke test.
FROM nginx:stable-alpine
COPY nginx.conf /etc/nginx/nginx.conf
RUN apk update && apk upgrade --no-cache && \
    mkdir -p /var/log/securelab && nginx -t
EXPOSE 80
