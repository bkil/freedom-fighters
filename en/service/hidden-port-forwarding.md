# Exposing HTTP servers within LAN to custom WAN clients

* The client will also need to run dedicated software to reach the server.
* Neither side should be required to pay a monthly subscription or run an exposed host themselves.
* See also: [public-port-forwarding.md](public-port-forwarding.md)

## Hosted FOSS client and server

### I2P

* https://en.wikipedia.org/wiki/I2P

### IPFS P2P

* https://github.com/ipfs/kubo/blob/master/docs/experimental-features.md#user-content-ipfs-p2p
* https://github.com/ipfs/kubo/blob/master/docs/experimental-features.md#user-content-p2p-http-proxy
* protocol: TCP, HTTP
* bearer: IPFS

### Spork

* https://github.com/atek-cloud/spork
* bearer: Hyperswarm

### Tor Onion service

* https://en.wikipedia.org/wiki/Tor_hidden_service#Onion_services
* https://en.wikipedia.org/wiki/Tor2web
* bearer: Tor

### Yggdrasil

* https://github.com/yggdrasil-network/yggdrasil-go

## FOSS client

### Tailscale

* https://tailscale.com/pricing/
* 20 devices, 1 user

### ZeroTier

* https://github.com/zerotier/ZeroTierOne

## Self-hosted FOSS client and server

* For these to work, you will need to run an additional, publicly reachable node

### autossh

* https://www.harding.motd.ca/autossh/

### GoTeleport.com

* https://goteleport.com/pricing/

### Nebula

* https://github.com/slackhq/nebula

### Tinc

* https://en.wikipedia.org/wiki/Tinc_(protocol)
