FROM almalinux:8

RUN dnf install nginx -y
RUN rm -f /usr/share/nginx/html/index.html

COPY qi/ /usr/share/nginx/html/

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]