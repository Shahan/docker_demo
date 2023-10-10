FROM openjdk:8

ENV WM_PACKAGE wiremock-jre8
ENV WM_VERSION 2.35.0

RUN mkdir /$WM_PACKAGE
WORKDIR /$WM_PACKAGE
RUN curl -sSL -o $WM_PACKAGE.jar https://repo1.maven.org/maven2/com/github/tomakehurst/$WM_PACKAGE-standalone/$WM_VERSION/$WM_PACKAGE-standalone-$WM_VERSION.jar

COPY resources/__files /$WM_PACKAGE/__files
COPY resources/mappings /$WM_PACKAGE/mappings

EXPOSE 8443 8080

ENTRYPOINT java -jar $WM_PACKAGE.jar --port 8080 --https-port 8443 > log.txt
