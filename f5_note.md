# F5
- F5 App Delivery Controllers(ADSs)
- package by package
    - Client - ASA - server
    - L4: IP:port
    - data package giu nguyen: chi sua IP source dest
- full proxy design: inherit pacakage by package + more advance: L4 + l7
    - insert cert, ssl
- Client -> F5: | server + client | -> server BE
    - package processing: read the package and processing

- F5: feature: use TMOS(traffic management OS)
    - TCP Express: optimize in L4 
        - hardware
        - software
    - proxy application faster: process in L7:
        - ssl offset
        - timeout
        - size of package
    - IRule
        - rewrite url
        - classify package traffic

- dnsrate limit

- Linux(kernel) # TMOS?
    - CPU different:
    - TMOS is optimize, CPU is modify 

- license + image bundle
    - 200M -> image 200M
    - 1G -> image 1G

- F5 Synthesis
    - LTM, GTM ...
    - irules, iapp, icall, icontrol
    - TMOS
    - Appliance, Chassis, Virtual Edition
    - Network: Physical, Overlay, SDN
