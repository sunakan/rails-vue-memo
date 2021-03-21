FROM ruby:3-slim
WORKDIR /var/local/app/

# 後で全部繋げる
RUN apt-get update
RUN apt-get install -y ruby-dev
RUN apt-get install -y make
RUN apt-get install -y build-essential
RUN apt-get install -y libpq-dev
RUN apt-get install -y curl
# [nodejs](https://github.com/nodesource/distributions/blob/master/README.md#installation-instructions)
RUN curl -fsSL https://deb.nodesource.com/setup_14.x | bash -
RUN apt-get install -y nodejs
RUN npm install -g yarn
