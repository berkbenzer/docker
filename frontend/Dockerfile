## Build phase
FROM node:16-alpine  as builder
WORKDIR '/usr/app'
COPY package.json .
RUN npm install
COPY . . 
RUN npm run build

## Second Phase
FROM nginx
COPY --from=builder /usr/app/build /usr/share/nginx/html


## docker build .
## docker run -p 8080:80 CONTAINER_ID 
              ## 8080 from outside
              ## 80 Nginx default port 