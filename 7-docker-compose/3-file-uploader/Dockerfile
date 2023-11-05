FROM node:14-slim
WORKDIR /uploader-app
COPY app/. .
RUN npm install
EXPOSE 4000
CMD [ "node", "server.js" ]