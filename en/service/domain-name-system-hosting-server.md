# Domain name system hosting

* https://en.wikipedia.org/wiki/DNS_hosting_service
* https://en.wikipedia.org/wiki/List_of_managed_DNS_providers

## Free

### ClouDNS

* https://www.cloudns.net/managed-dns/
* 4 unicast DNS servers: Amsterdam, Virginia, Paris, Frankfurt
* 1 DNS zone
* free subdomain: cloudns.ph, cloudns.nz
* 50 DNS records
* 500k query/months
* 1 mail forward
* dynamic DNS
* web redirects
* 2FA
* 1h TTL

### F5

* https://www.f5.com/cloud/pricing
* operator: Volterra
* load balancing
* 120s health check
* 2 endpoints origin servers
* global anycast IP
* TLS certificate
* 1 DNS zone
* 1000 DNS record
* 1 Distributed Cloud App Stack App Deliver Network container per PoP, 1 vCPU, 1GB RAM, 5GB storage
* 1 delegated domain

### FreeDNS

* https://freedns.afraid.org/signup/features/
* 20 subdomains
* records: CNAME, A, AAAA, MX, NS, TXT, LOC, RP, HINFO, SRV, CAA
* web redirect, cloaking (rewrite?)
* dynamic DNS

### GCore

* https://gcore.com/pricing
* Google reCAPTCHA for registration, but not for login, billing address information required
* 1 Geo RRset
* unlimited zones
* unlimited request/month
* 60s minimum TTL
* dynamic RRset: 3 records (1 RRset per zone)
* failover: 1 RRset, 300s poll frequency
* minimum TTL 120s

### GeoScaling DNS2

* https://www.geoscaling.com/
* 1M request/month
* 300s TTL
* dynamic DNS
* AXFR zone transfer
* dynamic redirection: country, city, ASN, failover, server load balancing via API, custom PHP-like scripts

### Hosted.name

* https://hosted.name/
* jurisdiction: United Kingdom
* 8 domain
* unlimited query/month

### NameCheap

* https://www.namecheap.com/domains/freedns/
* email forwarding
* dynamic DNS

### NS1

* https://ns1.com/plans
* operator parent company: IBM
* 500k query/month
* 50 records
* API, integrations, 1 filter chain, 1 built-in monitor

### Zilore

* https://zilore.com/en/dns
* 5 domains
* 1000 record/domain
* jurisdiction: United Kingdom
* 1M query/month
* anycast DNS
* DDoS protection
* IPv4 & IPv6
* min 15m TTL
* OTP 2FA
* the SOA record includes an email address where the @-sign is not escaped, thus failing validation

### Zonomi

* https://zonomi.com/
* operator: Rimuhosting
* jurisdiction: New Zealand
* 1 DNS zone (domain)
* 10 DNS records
* 1M query/month
* PoP: London, Dallas, New York and Auckland
* software: PowerDNS
* low TTL
* record types: A, AAAA, MX, CNAME, PTR, SRV, TXT
* wildcard records
* dynamic DNS (HTTP GET)
* DNS API
* failover integrated with pingability.com
* custom vanity name server
* DNSSec
* apex/bare/root domain aliases
* no credit card for registration

## Oligopoly

### Cloudflare

https://www.cloudflare.com/dns/
