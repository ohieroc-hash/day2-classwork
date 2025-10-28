#stage 1: build app

FROM node:alpine as build

WORKDIR /app

COPY package*.joson ./

RUN npm install

COPY . .

RUN npm run build

#stage 2: render app with nginx

FROM nginx:alpine

COPY --from=build /app/dist /usr/share/nginx/htm1

EXPOSE 80

CMD ["nginx", "-g", "daemon off:]
    




