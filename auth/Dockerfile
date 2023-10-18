FROM ubuntu:22.04

WORKDIR /app

COPY package*.json .

# RUN apt-get update && \
#     apt-get install -y curl && \
#     apt-get install -y nodejs npm && \
#     npm install

RUN sed -i 's/htt[p|ps]:\/\/archive.ubuntu.com\/ubuntu\//mirror:\/\/mirrors.ubuntu.com\/mirrors.txt/g' /etc/apt/sources.list
RUN apt-get update -y
RUN apt-get install -y curl
RUN apt-get install -y nodejs
RUN apt-get install -y npm
RUN npm install

COPY login.html .
COPY signup.html .
COPY app.js .

EXPOSE 3000

CMD ["node", "app.js", "&"]
