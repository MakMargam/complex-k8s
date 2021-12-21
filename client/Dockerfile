FROM node:16-alpine as builder

RUN mkdir -p /app

WORKDIR /app
COPY ./package.json .
RUN npm install
RUN ls
COPY . .


RUN npm build --prod


# CMD [ "npm", "start","--host", "0.0.0.0", "--port", "3000" ]  


# production environment
FROM nginx:1.17.1-alpine
EXPOSE 3000
COPY --from=builder /app/build /usr/share/nginx/html
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
RUN pwd
RUN ls
# new
# COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf
# CMD ["nginx", "-g", "daemon off;"]