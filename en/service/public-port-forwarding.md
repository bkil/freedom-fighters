# Publicly exposing-fronting HTTP servers within LAN

* The server may not have a publicly reachable port
* The client may be just a web browser without anything else installed
* Neither side should be required to pay a monthly subscription or run an exposed host themselves.
* See also: [hidden-port-forwarding.md](hidden-port-forwarding.md)

## Self-hosted FOSS client and server

### Chisel

* https://github.com/jpillora/chisel
* link: HTTP (encrypted using SSH)
* service: UDP, TCP, SOCKS5, HTTP CONNECT proxy

### FRP

* https://github.com/fatedier/frp
* link: UDP (KCP), QUIC, TCP, optional TLS, HTTP_PROXY, HTTP CONNECT
* service: UDP, TCP, HTTP, HTTPS

### go-http-tunnel

* https://github.com/mmatczuk/go-http-tunnel
* link: HTTP 2.0
* service: TCP, HTTP, vhosting, SNI
* authorization: client TLS certificates

### SirTunnel

* https://github.com/anderspitman/SirTunnel
* link: SSH
* service: HTTP, HTTPS

### sshuttle

* https://github.com/sshuttle/sshuttle
* link: SSH
* service: SSH, transparent proxy

## Hosted FOSS client and server

### Expose.dev

* https://github.com/beyondcode/expose
* link: WebSocket
* service: HTTP, HTTPS
* random subdomain

### LocalTunnel.me

* https://github.com/localtunnel/localtunnel
  * https://github.com/localtunnel/server
* link: TCP
* service: HTTP, HTTPS

### Pangolin

* https://github.com/fosrl/pangolin
* https://pangolin.fossorial.io/auth/signup
* link: WireGuard
* service: UDP, TCP, HTTP, HTTPS

### sish

* https://github.com/antoniomika/sish
* link: SSH
* service: TCP, HTTP, HTTPS, WebSocket, WSS, vhosting, SNI

### Telebit.Cloud

* https://telebit.cloud/
* https://git.coolaj86.com/coolaj86/telebit.js
* link: WebSocket
* service: TCP, HTTP, HTTPS

### tunneller

* https://github.com/skx/tunneller
* link: MQTT (mosquitto)
* service: HTTP

## FOSS client

### jprq

* https://github.com/azimjohn/jprq
* link: TCP
* service: TCP, HTTP

### localhost.run

* https://localhost.run/
* https://medium.com/localhost-run/localhost-run-the-origin-story-5aeaf5692dee
* link: SSH
* service: TCP, HTTP
* adds TLS

### ngrok.com

* https://ngrok.com/pricing
* https://github.com/sleirsgoevy/ngrok-free
* link: TCP
* service: TCP, HTTP
* adds TLS
* 1 port
* up to 40 requests/minute

### OpenPort.io

* https://openport.io/pricing
  * https://github.com/openportio/openport-go
  * https://github.com/openportio/openport
* link: HTTP (?)
* service: TCP, HTTP
* 10MB/month traffic
* 1 device, 1 connection per device
* 1 day connection timeout

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

### Packetriot.com

* https://packetriot.com/
* link: HTTP/HTTPS (?)
* service: TCP, HTTP, HTTPS, SNI vhosting
* 1 port
* 1GB/month traffic

### Staqlab-tunnel

* https://github.com/cocoflan/Staqlab-tunnel
* link: SSH

### UltraHook.com

* https://www.ultrahook.com/faq
* link: HTTPS
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
* https://serveo.net/
