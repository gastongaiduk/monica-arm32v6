#FROM monica:fpm-alpine AS monica
FROM arm32v6/monica:fpm-alpine AS monica

#FROM nginx:alpine
FROM arm32v6/nginx:alpine

COPY nginx.conf /etc/nginx/nginx.conf

# Copy content of monica image
COPY --from=monica /var/www/html /var/www/html
RUN ln -sf /var/www/html/storage/app/public /var/www/html/public/storage
