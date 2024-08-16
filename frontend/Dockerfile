FROM node:alpine AS builder

LABEL company="Gopenux LAB"
LABEL autor="Nestor Cabrera"

WORKDIR /src

COPY package*.json ./

RUN npm install


FROM node:alpine AS estaticos

WORKDIR /src

COPY --from=builder /src/node_modules /src/node_modules

COPY . . 

RUN npm run build



FROM nginx:alpine AS produccion

WORKDIR /src

COPY --from=estaticos /src/build /usr/share/nginx/html

EXPOSE  80

CMD ["nginx", "-g", "daemon off;"]
