# Bitcoin Core

* Creates virtual server(s) with docker
* Creates cloud volume(s) and mount to /srv
* Register server(s) in domain `var.domain`
* Creates cloud firewall and apply network policy to server(s)
* Deploy bitcoin-core in `/srv/<var.name>`

## Components

*Bitcoin Core* is programmed to decide which block chain contains valid transactions. The users of Bitcoin Core only accept transactions for that block chain, making it the Bitcoin block chain that everyone else wants to use. For the latest developments related to Bitcoin Core, be sure to visit the project’s [official website](https://bitcoincore.org/).

* Original software git repo: <https://github.com/bitcoin/bitcoin.git>
* Docker image git repo: <https://github.com/4ops/bitcoin-core.git>

## Cloud resources

* DigitalOcean droplet
* DigitalOcean volume
* DigitalOcean cloud firewall

## Default firewall rules

### Incoming

* Allow SSH from `var.trusted_sources`
* Allow tcp/8332 from `var.trusted_sources`
* Allow tcp/8333 from world
* Allow tcp/18332 from `var.trusted_sources`
* Allow tcp/18333 from world

### Outgoing

* Allow tcp to world
* Allow udp to world
* Allow icmp to world
