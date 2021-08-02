FROM node:12-alpine
COPY --chown=node:node . /src
WORKDIR /src
CMD ["node", "index.js"]

# and then run
# docker build --tag=incrementor .
# docker run incrementor
# file not found, writing '0' to a new file

# docker run incrementor
# file not found, writing '0' to a new file

# ➜  volumes git:(master) ✗ docker run --env DATA_PATH=/data/num.txt --mount type=volume,src=incrementor-data,target=/data incrementor

# 0
# ➜  volumes git:(master) ✗ docker run --env DATA_PATH=/data/num.txt --mount type=volume,src=incrementor-data,target=/data incrementor

# 1
# ➜  volumes git:(master) ✗ docker run --env DATA_PATH=/data/num.txt --mount type=volume,src=incrementor-data,target=/data incrementor

# 2
# ➜  volumes git:(master) ✗ docker run --env DATA_PATH=/data/num.txt --mount type=volume,src=incrementor-data,target=/data incrementor

# 3

# somehow state was maintained

# commons use case: logs

# want database states written out