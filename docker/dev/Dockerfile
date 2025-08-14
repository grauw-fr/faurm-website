FROM node:22-alpine

ENV NODE_ENV development

WORKDIR /usr/src/app

COPY . .

COPY docker/dev/bash/entrypoint.sh /etc/entrypoint.sh
RUN chmod +x /etc/entrypoint.sh

EXPOSE 5173

ENTRYPOINT ["/etc/entrypoint.sh"]