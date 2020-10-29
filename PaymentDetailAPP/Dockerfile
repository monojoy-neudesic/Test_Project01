FROM node:14.2.0-alpine3.11 as build
WORKDIR /app

RUN npm install -g @angular/cli

COPY package.json ./
RUN npm install
COPY . .
RUN ng build --prod

FROM nginx:1.19.3-alpine as runtime
COPY --from=build /app/dist/PaymentDetailAPP /usr/share/nginx/html
