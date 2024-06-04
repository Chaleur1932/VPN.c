firstly run `docker-compose up`, configure the docker-compose.yml according to you architecture, this repo is an arm64 version.

10.0.2.6 10.0.2.7 are clients，10.0.2.8 is the router，LAN contains two hosts named 192.168.60.101 192.168.60.102

if the images contain no gcc libssl vim, remember to apt-get them

generate the certs separately for server and client in ./cert_server & ./ca_client

change the code in client, make CA check from PEER to NONE

`gcc -o vpnclient/server client.c/server.c -lssl -lcrypto -lcrypt`

run `./vpnclient seed dees 192.168.78.xx`，this IP for tun0 can be arbitrarily assigned

run `./vpnserver`

`ping 192.168.60.xx` is available
