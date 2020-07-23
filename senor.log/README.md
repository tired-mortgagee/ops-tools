1. Prepare directory on container host
```
mkdir /var/logroot
mkdir /var/logroot/upload
chmod 777 /var/ftproot/upload
```
2. Build
```
docker build --rm -t senor.log --network host .
```
3. Run
```
docker run -d -p 514:514/udp -v /var/logroot:/var/logroot -t senor.log
```
