#### Common Useful Filters
Filter | Use
--- | ---
icmp | filters packets captured during ping
not arp / not http | filter selected protocal
udp only / tcp only | shows only selected protocal
tcp.port == 8080 | shows http requests on port 8080
not arp and !(udp.port == 53) | Combined Filter
http.request.method == POST and tcp.port == 9000 | Shows POST request sent to port 9000

##### View MAC Address during Packet Capture
![Screenshot at 2022-12-21 10-24-58](https://user-images.githubusercontent.com/85208639/208824082-20fee7c4-e5d1-4ffa-9166-3ebf961b5fe1.png)
![Screenshot at 2022-12-21 10-26-43](https://user-images.githubusercontent.com/85208639/208824101-d38364f9-91dc-46d9-ab33-0675b1f41f84.png)
