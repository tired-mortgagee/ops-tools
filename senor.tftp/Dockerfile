FROM alpine:3.12

RUN apk add --no-cache tftp-hpa

VOLUME /var/tftproot

EXPOSE 69/udp

CMD ["in.tftpd", "--foreground", "--create", "--secure", "/var/tftproot"]
