# Optimization ideas

## busybox inetd

Only keep services in memory while they are serving requests.

* https://github.com/brgl/busybox/blob/abbf17abccbf832365d9acf1c280369ba7d5f8b2/networking/inetd.c

## Parental controls

It would be very useful to have a tiny MITM HTTPS proxy running for such purpose along with what can already be done through the VLAN, firewall, ipset and DNS.

* https://openwrt.org/docs/guide-user/firewall/fw3_configurations/fw3_parent_controls
* https://openwrt.org/docs/guide-user/services/proxy/overview
* https://openwrt.org/docs/guide-user/services/proxy/tinyproxy
* https://reddit.com/r/selfhosted/comments/piarcj/selfhosted_parental_control/
