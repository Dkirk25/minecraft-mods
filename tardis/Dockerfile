FROM openjdk:8-jre-slim-buster

COPY . /minecraft/ 

WORKDIR /minecraft

RUN apt-get update \
  && apt-get install -y --no-install-recommends curl unzip tar\
  && apt-get install nano -y \
  && chmod +x startup.sh

WORKDIR /minecraft

EXPOSE 26650/udp
EXPOSE 26650/tcp

CMD ["./startup.sh"]