FROM nginx:1.23-alpine

RUN apk add --no-cache openssl
RUN apk add --no-cache bash


ARG DOMAINS
ARG CERTBOT_TEST_CERT
ARG CERTBOT_EMAILS
ARG CERTBOT_RSA_KEY_SIZE

ENV DOMAINS=$DOMAINS
ENV CERTBOT_TEST_CERT=$CERTBOT_TEST_CERT
ENV CERTBOT_EMAILS=$CERTBOT_EMAILS
ENV CERTBOT_RSA_KEY_SIZE=$CERTBOT_RSA_KEY_SIZE

COPY gzip.conf hsts.conf /etc/nginx/includes/
COPY ./default.conf /etc/nginx/conf.d/



# Expose the listening port
EXPOSE 80


# Launch NGINX
CMD [ "nginx", "-g", "daemon off;" ]
