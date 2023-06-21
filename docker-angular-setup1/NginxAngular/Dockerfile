FROM node:alpine as builder
WORKDIR /usr/src/app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
RUN npm run build --prod

# nginx service
FROM nginx:alpine
COPY --from=builder /usr/src/app/dist/NginxAngular/ /usr/share/nginx/html

