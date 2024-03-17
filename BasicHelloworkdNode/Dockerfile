FROM nodejs:alpine

LABEL Devops="Anup"

WORKDIR /usr/nodeapp

ADD https://github.com/AnupDudhe/nodejs-on-ec2.git  .

WORKDIR nodejs-on-ec2 

EXPOSE 8000
RUN npm install 
CMD ["npm" , "start"]
