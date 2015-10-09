# helpful-tools
Personal collection of scripts, snippets, and more, typically written in ruby.

## Tools

### network-scanner

I needed a tool to find a repeater / router on the subnet, where repeater was not doing NAT, and was simply a pass through (so it could have any address the upstream DHCP server gave to it). 

Using this tool, you can pretty quickly find all IPs that respond to HTTP, or are pingable, on any subnet.

```bash
usage: scan-network subnet [ action_type [ action_params ] ]
       scan-network subnet [ --http | --ping [count] ]
   eg: scan-network 172.16.100.1/24 --ping 3
       scan-network 192.168.0.0/16 --http

       note: --http is the default scan method
```

Example:
```bash
|11:16:07| → ./scan-network 172.16.100.1/24 --http
Note: total 256 IPs in this range
Check starting...
172.16.100.46 responded
172.16.100.71 responded
.... [ etc ] ...
```
