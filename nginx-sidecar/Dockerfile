FROM nginx:1.17.8-alpine
RUN apk add --no-cache gettext
COPY default.template /etc/nginx/conf.d
EXPOSE 80
CMD envsubst '\$NGINX_LISTEN_PORT \$NGINX_PROXY_HOST \$NGINX_PROXY_PORT \$NGINX_REWRITE' < /etc/nginx/conf.d/default.template > /etc/nginx/conf.d/default.conf && cat /etc/nginx/conf.d/default.conf && exec nginx -g 'daemon off;'