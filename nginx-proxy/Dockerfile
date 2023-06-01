FROM nginx:alpine

COPY ./nginx.conf /etc/nginx/conf.d/nginx.conf

EXPOSE 80/tcp

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]