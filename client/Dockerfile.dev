FROM node:12-alpine as build

RUN mkdir -p /app

WORKDIR /app

COPY . .

RUN npm install

# RUN npm run build --prod


CMD [ "npm", "start","--host", "0.0.0.0", "--port", "3000" ]  


# production environment
# FROM nginx:1.17.1-alpine
# COPY --from=build /app/build /usr/share/nginx/html
# new
# COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf
# EXPOSE 80
# CMD ["nginx", "-g", "daemon off;"]