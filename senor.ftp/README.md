1. Prepare directory on container host
`mkdir /var/ftproot`
`mkdir /var/ftproot/upload`
`chmod 777 /var/ftproot/upload`

2. Build
`docker build --rm -t senor.ftp --build-arg PASV_ADDRESS=<IP_ADDRESS> .`

3. Run
`docker run -d -p 20-21:20-21/tcp -p 10090-10100:10090-10100/tcp -v /var/ftproot:/var/ftproot -t senor.ftp`
