# Publicly exposing-fronting HTTP servers within LAN

* The server may not have a publicly reachable port
* The client may be just a web browser without anything else installed
* Neither side should be required to pay a monthly subscription or run an exposed host themselves.
* See also: [hidden-port-forwarding.md](hidden-port-forwarding.md)

## Self-hosted FOSS client and server

## Hosted FOSS client and server

### LocalTunnel.me

* https://github.com/localtunnel/localtunnel

### sish

* https://github.com/antoniomika/sish
* link: SSH, HTTP, vhosting, SNI
* service: TCP

## FOSS client

### localhost.run

* https://localhost.run/
* https://medium.com/localhost-run/localhost-run-the-origin-story-5aeaf5692dee
* link: SSH
* service: TCP, HTTP
* adds TLS

### ngrok.com

* https://ngrok.com/pricing
* https://github.com/sleirsgoevy/ngrok-free
* TCP, HTTP
* adds TLS
* 1 port
* up to 40 requests/minute

### Portmap.io

* https://portmap.io/
* link: OpenVPN
* service: UDP, TCP, HTTP

## Proprietary client and server

### CloudFlare Tunnels

* https://developers.cloudflare.com/pages/how-to/preview-with-cloudflare-tunnel
* https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/do-more-with-tunnels/trycloudflare/

### localxpose.io

* https://localxpose.io/#pricing
* 4 active tunnels
* service: HTTP, HTTPS
* 15 minute tunnel timeout
* "Interstitial page"

### OpenPort.io

* https://openport.io/pricing
* service: TCP, HTTP
* 10MB/month traffic
* 1 device, 1 connection per device

### Packetriot.com

* https://packetriot.com/
* service: TCP
* 1 port
* 1GB/month traffic

### UltraHook.com

* https://www.ultrahook.com/faq
* service: HTTP POST only

### WebhookRelay.com

* https://webhookrelay.com/pricing/
* service: HTTP POST, HTTP (bidirectional tunnels)
* 1 endpoint, up to 2 destination
* up to 150 request per month

### Yaler.net

* https://yaler.net/start
* service: web, SSH
* 1 relay domain
* 1GB/month traffic

# Unmaintained

* https://www.npmjs.com/package/beame-gatekeeper
* https://github.com/beameio
* https://pagekite.net/pricing/
* https://github.com/azimjohn/jprq
* https://serveo.net/
