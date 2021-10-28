#### Setting up clients

The number of clients to generate cryptographic keys for is configured with the `PEERS=<num.of.peers>` environmental variable. Configuration files for the clients will be located at `/home/pi/wireguard/config/` folder. Copy the `peer1/peer1.conf` file to your client and use that to establish the VPN tunnel.

For mobile phone clients, a QR code can generated using the command - 
``` bash
docker exec -it wireguard /app/show-peer <peer-number>
```

### Adding more clients
Increment the `PEERS` environmental variable in the `docker-compose.yml` file and recreate the container using - 

``` bash
docker-compose up -d --force-recreate
```