FROM node:16.15.0-alpine3.15 as build-stage

WORKDIR /usr/src/app

ENV REACT_APP_BACKEND_URL=http://localhost:8080

COPY . .

RUN npm install && npm run build


FROM nginx:1.19-alpine

COPY --from=build-stage /usr/src/app/build /usr/share/nginx/html
