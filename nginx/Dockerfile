FROM nginx:1.17.10

EXPOSE 80 443

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    rm -rf /var/lib/apt/lists/*

RUN apt-add-repository -r -y ppa:certbot/certbot && apt-get update

RUN apt-get install -y python-certbot-nginx