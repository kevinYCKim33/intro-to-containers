# build stage
FROM node:12-stretch AS build
WORKDIR /build
COPY --chown=node:node package-lock.json package.json ./
RUN npm ci
COPY . .

# runtime stage
FROM alpine:3.10
RUN apk add --update nodejs
RUN addgroup -S node && adduser -S node -G node
USER node
RUN mkdir /home/node/code
WORKDIR /home/node/code
# everything you got from node, put into build
COPY --from=build --chown=node:node /build .
CMD ["node", "index.js"]

# it breaks but big idea:
# you don't really need node for your build file
# doing this command just takes whatever is in node, and puts it out
# that way your production thing doesn't have useless junk
# even though this is so trivial that you wouldn't really do this
