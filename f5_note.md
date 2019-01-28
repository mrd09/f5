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

----------------------
Day 2:
2.1 Persistence
- BIG-IP LTM
- Persistence:
    - IP: Source Address  Affinity Persistence: Support TCP UDP traffic, base on client IP: source /16...
        + mass of IP => increase system assign resource to process
        + Not recommend to use
        + Use persistence record
    - Cookies persis
        + Method: insert, rewrite, passive
        + No need persistence record
    - hash mode

- Cookies: 
    + Payment 
    + Save user information when access to server

- Cookies: method insert:
    + client -> F5 -> server: only client and F5 exchange cookies: client <-- cookies --> F5, don't care server cookies
    1. client -- no cookies --> F5  -- no cookies --> server
    2. client <-- insert cookies -- F5  <-- no cookies -- server

- Cookies: method rewrite:
    1. client -- no cookies --> F5  -- no cookies --> server
    2. client <-- rewrite cookies -- F5  <-- blank cookies -- server
                    cookies < 4Kb

- Cookies: method passive:                   
    1. client -- no cookies --> F5  -- no cookies --> server
    2. client <-- server cookies -- F5  <-- server cookies -- server
                    cookies < 4Kb