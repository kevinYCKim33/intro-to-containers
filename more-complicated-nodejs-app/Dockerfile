FROM node:12-stretch

USER node

WORKDIR /home/node/code

# copy everything in this directoy into home/node/code
COPY --chown=node:node . .

# npm ci: will adhere to what's in package-lock.json
# recommended over npm install
# a best practice
RUN npm ci

# some people use for documentation
# or you could just do publish
# Brian Holt doesn't seem too sold on it
# https://btholt.github.io/complete-intro-to-containers/expose
# EXPOSE 3000

CMD ["node", "index.js"]