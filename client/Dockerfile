FROM node:12-alpine as build

RUN mkdir -p /app

WORKDIR /app
RUN npm install
RUN ls
COPY . .


RUN npm build --prod


# CMD [ "npm", "start","--host", "0.0.0.0", "--port", "3000" ]  


# production environment
FROM nginx:1.17.1-alpine
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
RUN ls
COPY --from=build /app/build /usr/share/nginx/html
# new
# COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf
# CMD ["nginx", "-g", "daemon off;"]