FROM node:13.12.0-alpine AS build
WORKDIR /app
COPY ./package.json /app
COPY ./package-lock.json /app
COPY ./src/ /app/src/
COPY ./public/ /app/public/
RUN npm install
RUN npm run build

FROM httpd:2.4 as prod
COPY --from=build /app/build /usr/local/apache2/htdocs/
EXPOSE 3000