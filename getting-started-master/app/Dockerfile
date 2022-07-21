# syntax=docker/dockerfile:1
##FROM node:12-alpine
##RUN apk add --no-cache python2 g++ make
##WORKDIR /app
##COPY package.json yarn.lock ./
##RUN yarn install --production
##CMD ["node", "src/index.js"]
##EXPOSE 3000


FROM maven AS build
WORKDIR /app
COPY . .
RUN mvn package

FROM tomcat
COPY --from=build /app/target/file.war /usr/local/tomcat/webapps 
