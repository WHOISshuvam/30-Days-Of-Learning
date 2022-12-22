#### Stages of Penetration Test

>While performing tests minimal impact must be done on clients system and network.

Engagement | Information Gathering | Footprinting | Vulnerability Assesement | Exploitation | Reporting
| --- | --- | --- | --- | --- | ---|

#### Notes :
> Scope : IP Address, Network Block, Domain Names 
> Only after legal documents are signed the penetration test should be performed.
> Collect information about employees, company location, board of directors. Extracted information can be used for social engineering if allowed in ROE.
> For eg. if the scope is whole company collect CIDR, ips, domains, try zone transfer, find live hosts, enumerate web servers, operating system.
> Use information collected in previous step perform portscan, directory bruteforce, use automated tools like burp, nikto, nessus, to find scan hosts.
> Perform mannual testing side by side.
>Try exploiting vulnerabilties identified in previous step and finally the report is created.
