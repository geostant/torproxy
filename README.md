### **Simple TOR Proxy**
To run it :
`docker run -d --restart always -p 9050:9050 --name torproxy torproxy:latest`

You can follow the container logs to determine when it finally connects to TOR circuit (takes about 1 minute) with the following command:
`docker logs -f <container_name OR id>`

To exit just hit the `ctrl+c`

After the container finished to bootstrap, you can test it with :
`curl --socks5 localhost:9050 ifconfig.io`

You expect to see a different IP than your public one.

Last step, is to set your browser's socks proxy to point to localhost:9050 and you're good to go.
