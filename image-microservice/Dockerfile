FROM node:alpine AS build

LABEL company="Gopenux LAB"
LABEL autor="Nestor Cabrera"

WORKDIR /app/

COPY package.json ./

RUN npm install


FROM node:alpine AS pro

WORKDIR /app

COPY --from=build /app/node_modules /app/node_modules

COPY . .

CMD ["npm","start"]

EXPOSE 3001
