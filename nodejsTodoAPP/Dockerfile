
FROM ubuntu:latest

LABEL app = "todoAPP"

RUN sudo apt update 

RUN apt install node npm -y

RUN git clone https://github.com/owanhunte/nodejs-chat-app.git

WORKDIR nodejs-chat-app 

RUN npm install

EXPOSE 3000

CMD ["npm" , "start"]