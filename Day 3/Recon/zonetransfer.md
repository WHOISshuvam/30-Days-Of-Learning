### Zone Transfer
Whenever any change is made to DNS record, zone data changes are saved on Primary DNS server. Secondary DNS server holds the copy of Primary DNS server.
When there is any change to the zone data of Primary DNS, the data is shared with Secondary DNS server. This process is refered as zone transfer. Attacker can perform zone transfer to find hidden subdomains, DNS data, mail server,etc. Zone transfer shouldn't be possible from primary nameserver to unauthorized server.

#### Types :

| Full zone transfer | Incremental zone transfer |
|---|---|
|AXFR (Requires no Authentication)|IXFR|

#### Find  Nameservers
```
dig -t ns zonetransfer.me
;; ANSWER SECTION:
zonetransfer.me.	6817	IN	NS	nsztm2.digi.ninja.
zonetransfer.me.	6817	IN	NS	nsztm1.digi.ninja.
```

#### Performing Zone Transfer on Primary Name Server
```
dig  AXFR zonetransfer.me @nsztm1.digi.ninja
```

#### Using Zone-Transfer to find information about internal dns 

```
dig AXFR int @z.hackycorp.com
```
