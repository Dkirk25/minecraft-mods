FROM openjdk:8-jre-slim-buster

COPY . /minecraft/ 

WORKDIR /minecraft

RUN apt-get update \
  && apt-get install -y --no-install-recommends curl unzip tar\
  && apt-get install nano -y \
  # && curl https://download.nodecdn.net/containers/reforged/server/release/9.1.5/serverpack915.zip  -o serverpack915.zip \
  # && unzip serverpack915.zip \
  # && rm serverpack915.zip \
  && chmod +x startup.sh

# RUN mv forge-1.16.5-36.2.35-installer.jar forge-1.16.5-36.2.35.jar

# RUN sed -i "s|java -server -Xmx4G -Xms4G -jar forge-1.16.5-36.2.35.jar nogui|#!/bin/bash\njava -server -Xmx4G -Xms4G -Dfml.queryResult=confirm -jar forge-1.16.5-36.2.35.jar nogui |g" ServerStart.sh

# RUN sed -i "s|eula=false|eula=true |g" eula.txt
WORKDIR /minecraft

EXPOSE 26650/udp
EXPOSE 26650/tcp

CMD ["./startup.sh"]