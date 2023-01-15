FROM node:18

WORKDIR /usr/src/app

COPY package.json ./
COPY pnpm-lock.yaml ./

RUN pnpm install

COPY . .

RUN pnpm prisma migrate deploy
RUN pnpm run build

CMD [ "node", "dist/src/main.js" ]
