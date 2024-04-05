FROM node:20-alpine3.19

WORKDIR /usr/src/app

COPY package.json package-lock.json ./

RUN npm ci

COPY . .

RUN npm run build

COPY . ./dist

RUN npx prisma generate

EXPOSE 	3333

CMD [ "npm", "start" ]