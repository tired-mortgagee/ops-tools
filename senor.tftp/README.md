1. Prepare directory on container host

   mkdir /var/tftproot
   mkdir /var/tftproot/upload
   chmod 777 /var/tftproot/upload

2. Build

    docker build --rm -t senor.tftp .

3. Run

    docker run -d -p 69:69/udp -v /var/tftproot:/var/tftproot -t senor.tftp
