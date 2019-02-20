FROM node:alpine as client
WORKDIR "/app"
COPY ./package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 80 
COPY --from=client /app/build usr/share/nginx/html