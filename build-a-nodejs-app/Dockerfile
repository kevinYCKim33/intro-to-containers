FROM node:12-stretch

# creator of node docker made a user node so it's not user root with all the power
USER node

# make a work directory so it's not at the root
WORKDIR /home/node/code

# below USER so this guy is the guy who runs this and not root
COPY --chown=node:node index.js index.js

# ADD vs COPY: 
# COPY use for just local copies; does less; less is better
# ADD: go off to network and download the file; unzip or tar things
ADD --chown=node:node index.js index.js


CMD ["node", "index.js"]