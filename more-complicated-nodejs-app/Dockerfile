FROM node:12-stretch

USER node

WORKDIR /home/node/code

# copy everything in this directoy into home/node/code
COPY --chown=node:node . .

# npm ci: will adhere to what's in package-lock.json
# recommended over npm install
# a best practice
RUN npm ci

CMD ["node", "index.js"]