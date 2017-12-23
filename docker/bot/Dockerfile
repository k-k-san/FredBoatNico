FROM openjdk:8-jdk-slim

ENV ENV docker

WORKDIR /root
RUN apt-get update && \
    apt-get -y install zip git && \
    git clone https://github.com/k-k-san/FredBoat.git && \
    mkdir /opt/FredBoat
ADD AbstractPlayer.java /root/FredBoat/FredBoat/src/main/java/fredboat/audio/player/
ADD Config.java /root/FredBoat/FredBoat/src/main/java/fredboat/

WORKDIR /root/FredBoat
RUN ./gradlew build

WORKDIR /opt/FredBoat
ADD NicoAudioSourceManager.java /opt/FredBoat/
RUN cp /root/FredBoat/FredBoat/build/libs/FredBoat.jar /opt/FredBoat/ && \
    javac -classpath FredBoat.jar NicoAudioSourceManager.java && \
    mkdir -p com/sedmelluq/discord/lavaplayer/source/nico && \
    mv NicoAudioSourceManager.class com/sedmelluq/discord/lavaplayer/source/nico/ && \
    zip -r FredBoat.jar com/sedmelluq/discord/lavaplayer/source/nico/NicoAudioSourceManager.class && \
    apt-get remove -y zip git && \
    rm -rf /root/FredBoat com NicoAudioSourceManager.java && \
#ADD config.yaml credentials.yaml /opt/FredBoat/

CMD ["java", "-jar", "-Xmx128m", "FredBoat.jar"]
