#### Common Useful Filters
Filter | Use
--- | ---
icmp | filters packets captured during ping
not arp / not http | filter selected protocal
udp only / tcp only | shows only selected protocal
tcp.port == 8080 | shows http requests on port 8080
not arp and !(udp.port == 53) | Combined Filter
http.request.method == POST and tcp.port == 9000 | Shows POST request sent to port 9000
