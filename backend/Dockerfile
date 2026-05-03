FROM node:18-slim
RUN apt-get update && apt-get install -y \
      libcurl4-openssl-dev \
      ca-certificates \
      build-essential \
      python3 \
      python3-pip \
    && rm -rf /var/lib/apt/lists/*
COPY ./ /usr/src
WORKDIR /usr/src
RUN yarn
RUN yarn generate
CMD ["./node_modules/.bin/ts-node", "./index.ts"]
