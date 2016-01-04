# Docker image: clarkc/rpi-nginx

FROM hypriot/rpi-alpine-scratch

RUN apk update && \
apk upgrade && \
apk add bash nginx && \
rm -rf /var/cache/apk/*

# The config files are in /etc/nginx/
# The doc root is at /usr/share/nginx/html/
# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log

EXPOSE 80 443

ENTRYPOINT ["nginx", "-g", "daemon off;"]
