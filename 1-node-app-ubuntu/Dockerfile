FROM ubuntu:18.04
RUN apt-get update
RUN apt-get install curl -y
RUN apt-get install nodejs -y
COPY . /opt/node-app/
ENV channel=AbdullahUbuntu
# Dosyamızı node ile çalıştırmamız gerekir. Bunun için birkaç yöntem vardır.

# -----------------------------1---------------------------------------
# CMD ["node", "/opt/node-app/index.js"]

# -----------------------------2---------------------------------------
WORKDIR /opt/node-app/
CMD ["node", "index.js"];

