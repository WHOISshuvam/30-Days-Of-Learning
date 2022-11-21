### Zone Transfer
Whenever any change is made to DNS record, zone data changes are saved on Primary DNS server. Secondary DNS server holds the copy of Primary DNS server.
When there is any change to the zone data of Primary DNS, the data is shared with Secondary DNS server. This process is refered as zone transfer.

#### Types :

| Full zone transfer | Incremental zone transfer |
|---|---|
|AXFR|IXFR|
