FROM openjdk:8-jre-slim

ENV ENV docker

RUN mkdir /opt/FredBoat

WORKDIR /opt/FredBoat
ADD FredBoat.jar config.yaml credentials.yaml /opt/FredBoat/

CMD ["java", "-jar", "-Xmx128m", "FredBoat.jar"]
