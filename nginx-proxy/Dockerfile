FROM nginx:alpine

COPY ./nginx.conf /etc/nginx/conf.d/nginx.conf

EXPOSE 80
EXPOSE 443
CMD ["/usr/sbin/nginx", "-g", "daemon off;"]