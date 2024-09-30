FROM node:22.9.0 AS build

WORKDIR /app

COPY . . 

RUN npm ci
RUN npm run build 

FROM nginx 

COPY ./nginx.conf /etc/nginx/nginx.conf

COPY --from=build /app/dist/angular /usr/share/nginx/html
