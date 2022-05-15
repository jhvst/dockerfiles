FROM alpine

RUN apk add npm chromium
RUN npm install --global @nota-lang/nota

RUN adduser -u 501 -g 1000 -D -H nota
RUN mkdir /nota
RUN chown 501:1000 /nota

USER nota
ENTRYPOINT [ "/usr/local/bin/nota" ]
CMD [ "--help" ]