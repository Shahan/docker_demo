FROM openjdk:8

ENV WM_PACKAGE wiremock-jre8

RUN mkdir /$WM_PACKAGE
WORKDIR /$WM_PACKAGE
COPY bin/wiremock-jre8-standalone-2.35.0.jar $WM_PACKAGE.jar
COPY resources/__files /$WM_PACKAGE/__files
COPY resources/mappings /$WM_PACKAGE/mappings

EXPOSE 8443 8080

ENTRYPOINT java -jar $WM_PACKAGE.jar --port 8080 --https-port 8443 > log.txt
