FROM library/node:9.0

ARG USER_ID=1000
ARG GROUP_ID=1000

COPY app/fireloop /home/nodejs
COPY docker/production-backend/entrypoint.sh /entrypoint.sh

RUN groupmod -g ${GROUP_ID:-1000} node \
  && usermod -u ${USER_ID:-1000} node \
  && chmod +x /entrypoint.sh

USER node

WORKDIR /home/nodejs

ENTRYPOINT [ "/entrypoint.sh" ]