FROM node:20-alpine

WORKDIR /app

RUN apk add --no-cache openssl openssl-dev libc6-compat

RUN chown -R node:node /app

COPY --chown=node:node package*.json ./
COPY --chown=node:node prisma ./prisma/

RUN npm install && npx prisma generate

COPY --chown=node:node . .

USER node

EXPOSE 4000

CMD ["npm", "start"]
