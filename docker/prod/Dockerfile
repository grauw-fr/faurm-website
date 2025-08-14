FROM node:22-slim AS builder

WORKDIR /app

COPY package.json package.json
COPY .npmrc .npmrc
RUN npm i

COPY . .
RUN npm run build

RUN npm prune --production

FROM node:22-slim AS prod
WORKDIR /app

COPY --from=builder /app/build ./build
COPY --from=builder /app/node_modules ./node_modules

EXPOSE 3000
CMD ["node", "build/index.js"]