FROM debian:buster

RUN apt-get update -y && \
    apt-get upgrade -y && \
    apt-get install -y nginx openssl && \
    openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
    -keyout /etc/ssl/private/nginx.key \
    -out /etc/ssl/certs/nginx.crt \
    -subj "/C=JP/ST=Tokyo/L=Minato-ku/O=42Tokyo, Inc./CN=example.com"

COPY conf/default /etc/nginx/sites-available/default

CMD ["nginx", "-g", "daemon off;"]
