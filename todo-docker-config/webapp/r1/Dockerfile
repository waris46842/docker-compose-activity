FROM node:alpine

RUN apk update
RUN apk add git

WORKDIR /root
RUN git clone https://github.com/natawutn/todo-webapp.git
WORKDIR /root/todo-webapp
RUN yarn install

EXPOSE 3000
ENV TODO_ENDPOINT http://todo:8000/
CMD  yarn start
