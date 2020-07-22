FROM alpine:3.12

ARG PASV_ADDRESS

RUN apk --no-cache add vsftpd

RUN echo "allow_writeable_chroot=YES" >> /etc/vsftpd/vsftpd.conf \
    && echo "anon_root=/var/ftproot" >> /etc/vsftpd/vsftpd.conf \
    && echo "anon_upload_enable=YES" >> /etc/vsftpd/vsftpd.conf \
    && echo "background=NO" >> /etc/vsftpd/vsftpd.conf \
    && echo "chroot_local_user=YES" >> /etc/vsftpd/vsftpd.conf \
    && echo "dirmessage_enable=YES" >> /etc/vsftpd/vsftpd.conf \
    && echo "ftpd_banner=Welcome to FTP Server" >> /etc/vsftpd/vsftpd.conf \
    && echo "listen_ipv6=NO" >> /etc/vsftpd/vsftpd.conf \
    && echo "local_enable=YES" >> /etc/vsftpd/vsftpd.conf \
    && echo "local_umask=022" >> /etc/vsftpd/vsftpd.conf \
    && echo "max_clients=10" >> /etc/vsftpd/vsftpd.conf \
    && echo "max_per_ip=5" >> /etc/vsftpd/vsftpd.conf \
    && echo "no_anon_password=YES" >> /etc/vsftpd/vsftpd.conf \
    && echo "passwd_chroot_enable=yes" >> /etc/vsftpd/vsftpd.conf \
    && echo "pasv_address=$PASV_ADDRESS" >> /etc/vsftpd/vsftpd.conf \
    && echo "pasv_enable=Yes" >> /etc/vsftpd/vsftpd.conf \
    && echo "pasv_max_port=10100" >> /etc/vsftpd/vsftpd.conf \
    && echo "pasv_min_port=10090" >> /etc/vsftpd/vsftpd.conf \
    && echo "seccomp_sandbox=NO" >> /etc/vsftpd/vsftpd.conf \
    && echo "write_enable=YES" >> /etc/vsftpd/vsftpd.conf

VOLUME /var/ftproot

EXPOSE 20-21 10090-10100

CMD ["/usr/sbin/vsftpd", "/etc/vsftpd/vsftpd.conf"]
