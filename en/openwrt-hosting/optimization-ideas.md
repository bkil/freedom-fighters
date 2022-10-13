# Optimization ideas

## Fewer memory resitent daemons

Only keep services in memory while they are serving requests. This could save in the order of 1MB of RAM for a typical system with basic services or much more if you installed unusual services with larger footprint.

Service daemons that can be eliminated via inetd:

* https://openwrt.org/docs/guide-user/base-system/dhcp.dnsmasq (DNS)
* https://openwrt.org/docs/guide-user/advanced/ntp_configuration#ntp_server
* https://openwrt.org/docs/guide-user/base-system/dropbear
* https://openwrt.org/inbox/howto/telnet_enable
* https://openwrt.org/docs/guide-user/services/webserver/start (and luci)
* https://openwrt.org/docs/guide-user/firewall/upnp/miniupnpd
* https://openwrt.org/docs/guide-user/services/print_server/start
* https://openwrt.org/docs/guide-user/services/scanner_server/start

Less common ones:

* https://openwrt.org/docs/guide-user/services/email/start
* XMPP (rawsontetley)
* https://openwrt.org/docs/guide-user/services/nas/start
* https://openwrt.org/docs/guide-user/services/media_server/start
* https://openwrt.org/docs/guide-user/services/nas/ftp.overview
* https://github.com/openwrt/packages/blob/master/net/atftp/Makefile
* https://openwrt.org/docs/guide-user/services/vpn/start
* https://openwrt.org/docs/guide-user/services/start
* https://openwrt.org/docs/guide-user/services/proxy/start
* https://openwrt.org/docs/guide-user/services/remote_control/ostiary.server
* https://openwrt.org/docs/guide-user/services/snmp/start

Life cycle could be handled via cron:

* udhcpc
* https://openwrt.org/docs/guide-user/services/ntp/client-server

The life cycle could be constrained otherwise:

* https://openwrt.org/docs/techref/odhcpd
* https://openwrt.org/docs/techref/netifd
* ubusd
* https://openwrt.org/docs/guide-user/services/remote_control/portknock.server
* urngd: Persisted unused entropy should be loaded upon startup to seed a deterministic RNG, then new entropy gathered for some time and then it can shut down

Implementation:

* There exist xinetd/inetd-compatible solutions for many of the above.
* Some of them would require straight-forward patching
* Others might need a new, simplified implementation

Drawbacks:

* This trades off resident memory consumption with performance and latency introduced by the start-up time of the given service every time a new request comes in.
* Compiling a service with busybox inetd-compatibility may increase the code size a bit.
* Parallelism of requests must be disabled or limited to fit a deterministic amount of RAM. (TODO: Could `ujail` help?)

References:

* https://github.com/brgl/busybox/blob/abbf17abccbf832365d9acf1c280369ba7d5f8b2/networking/inetd.c
* https://www.sqlite.org/althttpd/doc/trunk/althttpd.md
* https://www.acme.com/software/thttpd/benchmarks.html

## Parental controls

It would be very useful to have a tiny MITM HTTPS proxy running for such purpose along with what can already be done through the VLAN, firewall, ipset and DNS.

* https://openwrt.org/docs/guide-user/firewall/fw3_configurations/fw3_parent_controls
* https://openwrt.org/docs/guide-user/services/proxy/overview
* https://openwrt.org/docs/guide-user/services/proxy/tinyproxy
* https://reddit.com/r/selfhosted/comments/piarcj/selfhosted_parental_control/
