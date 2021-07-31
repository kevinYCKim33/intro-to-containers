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