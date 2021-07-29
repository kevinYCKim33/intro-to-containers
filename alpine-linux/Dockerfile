FROM node:12-alpine

USER node

WORKDIR /home/node/code

# Docker is smart
# if the moment it senses a change
# it will do everything below manually
# so let's say you changed index.js but didn't change any of your packages
# docker will first compare that these are the exact same...
COPY --chown=node:node package-lock.json package.json ./

# if these two files are different...then and only then will it run npm ci

# npm ci: will adhere to what's in package-lock.json
# recommended over npm install
# a best practice
RUN npm ci

# now this will run if only index.js changed
# we save doing an npm install this way...

# I guess the term for that is layering.
# copy everything in this directoy into home/node/code
COPY --chown=node:node . .


# some people use for documentation
# or you could just do publish
# Brian Holt doesn't seem too sold on it
# https://btholt.github.io/complete-intro-to-containers/expose
# EXPOSE 3000

CMD ["node", "index.js"]
# docker build -t my-node-app .
# docker inspect my-node-app
# my size is: 92644519 => 92.64 MB
# node stretch/debian much larger than node alpine
