# Docker container for CIAO PDS FHIR CIP
# Version 0.1

FROM ubuntu:14.04

MAINTAINER HSCIC

RUN apt-get update
RUN apt-get install -y openjdk-7-jdk git maven
RUN git clone https://github.com/nhs-ciao/ciao-pds-fhir.git
RUN cd ciao-pds-fhir ; mvn package

EXPOSE 8080

VOLUME ["/root/.ciao/"]

ENTRYPOINT ["java", "-jar", "ciao-pds-fhir/target/ciao-pds-fhir-0.0.1-SNAPSHOT-executable.jar"]