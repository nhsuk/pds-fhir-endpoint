# Docker container for TKW for Spine
# Version 0.2

FROM ubuntu:14.04

MAINTAINER HSCIC

RUN apt-get update
RUN apt-get install -y openjdk-7-jre unzip wget
RUN wget https://raw.githubusercontent.com/nhs-ciao/ciao-utils/master/contrib/tkw/getTKW.sh
RUN chmod +x getTKW.sh
RUN ./getTKW.sh Spine /opt/SpineTKW ciao-tkw

EXPOSE 4001

ENTRYPOINT ["java", "-jar", "/opt/SpineTKW/TKW.jar", "-simulator", "/opt/SpineTKW/config/SPINE_MTH_20111121/tkw.properties"]
