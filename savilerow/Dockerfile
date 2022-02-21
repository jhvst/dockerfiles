FROM alpine

RUN wget --no-check-certificate https://savilerow.cs.st-andrews.ac.uk/savilerow-1.9.1-linux.tgz
RUN tar -xvf savilerow-1.9.1-linux.tgz

WORKDIR /savilerow-1.9.1-linux

RUN apk add bash openjdk17-jre-headless
ENTRYPOINT [ "/savilerow-1.9.1-linux/savilerow" ]
CMD [ "-help" ]