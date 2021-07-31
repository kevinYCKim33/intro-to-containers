# https://btholt.github.io/complete-intro-to-containers/static-assets-project
# STATIC ASSETS PROJECT: 
# BIG IDEA: this CRA has TypeScript and SASS
# preprocessor languages that turn into something else
# if the only thing we want is to serve html/css/js 
# instead of JSX/SASS/TS which doesn't get used in the build file
# let's just host the built version on nginx docker?? what's going on?

FROM node:12-stretch AS builder
WORKDIR /app
COPY . .
RUN npm ci && npm run build

FROM nginx:1.17
COPY --from=builder /app/build /usr/share/nginx/html

# docker build -t static-app .
# docker run -p 8080:80 static-app
# and then if you visit localhost:8080 your app will be hosted by nginx

# NOTES
# The project is to make a multi-stage Dockerfile that build the project in one container and then serves it from a different container using NGINX. If you're not familiar with NGINX, fear not! It is a static file server, which is to say it take takes HTML, CSS, JS, images, fonts, etc. and serves them to your users. It handles all the serving and file headers for you. Using it can be accomplished in few steps. You'll use the nginx:latest (or nginx:alpine! up to you) container and copy just the newly built files, not everything (which is in the build directory inside of the CRA app) to /usr/share/nginx/html and the nginx will take care of the rest. The nginx container defines CMD in it and if you don't override it, it starts NGINX for you. Give it a shot! Once you've tried, come back here and we'll do the solution together. NGINX runs on port 80 by default, so you probably want to route that something like 8080 on your host machine (otherwise you have to run it as root which no one wants to do.)