# helpful-tools
Personal collection of scripts, snippets, and more, typically written in ruby.

## Tools

### network-scanner

I needed a tool to find a repeater / router on the subnet, where repeater was not doing NAT, and was simply a pass through (so it could have any address the upstream DHCP server gave to it). 

Using this tool, you can pretty quickly find all IPs that respond to HTTP, or are pingable, on any subnet.

```bash
|11:56:12| → ./network-scanner --help

usage: network-scanner subnet [ --http [timeout seconds] | --ping [count] ]
                              [ --verbose ] [ --help | -h ]

   eg: network-scanner 172.16.100.1/24 --ping 3 --verbose
       network-scanner 192.168.0.0/16  --http 1
       network-scanner 192.168.0.0/16  --http

       defaults – http, timeout is 3, count for ping is 3
```

Example:
```bash
|11:16:07| → ./scan-network 172.16.100.1/24
Total IPS: 16, from 172.16.100.32 to 172.16.100.47, using --http to check...

..............
172.16.100.46 responded
.
|11:16:23| → 
```
