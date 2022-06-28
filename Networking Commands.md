# Networking Commands

The operating system consists of various built-in, command-line networking utilities that are used for network troubleshooting. We will see various networking commands which are most essentials for every network administrator.

* `ifconfig` view all network interface settings

``` console
zold@Zold:~$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.27.169.20  netmask 255.255.240.0  broadcast 172.27.175.255
        inet6 fe80::215:5dff:fecd:a362  prefixlen 64  scopeid 0x20<link>
        ether 00:15:5d:cd:a3:62  txqueuelen 1000  (Ethernet)
        RX packets 150  bytes 208063 (208.0 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 144  bytes 9816 (9.8 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

* `ip addr show` display a list of all network interfaces and the associated ip address type the following command

``` console
zold@Zold:~$ ip addr show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: bond0: <BROADCAST,MULTICAST,MASTER> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 6e:b1:bd:ff:36:79 brd ff:ff:ff:ff:ff:ff
3: dummy0: <BROADCAST,NOARP> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether e2:36:42:8a:df:61 brd ff:ff:ff:ff:ff:ff
4: tunl0@NONE: <NOARP> mtu 1480 qdisc noop state DOWN group default qlen 1000
    link/ipip 0.0.0.0 brd 0.0.0.0
5: sit0@NONE: <NOARP> mtu 1480 qdisc noop state DOWN group default qlen 1000
    link/sit 0.0.0.0 brd 0.0.0.0
```

* `ping <Ip>` check the network connectivity between host and server/host

``` console
zold@Zold:~$ ping www.google.com
PING www.google.com (142.251.37.36) 56(84) bytes of data.
64 bytes from mrs09s13-in-f4.1e100.net (142.251.37.36): icmp_seq=1 ttl=116 time=77.5 ms
64 bytes from mrs09s13-in-f4.1e100.net (142.251.37.36): icmp_seq=2 ttl=116 time=84.1 ms
64 bytes from mrs09s13-in-f4.1e100.net (142.251.37.36): icmp_seq=3 ttl=116 time=77.8 ms
64 bytes from mrs09s13-in-f4.1e100.net (142.251.37.36): icmp_seq=4 ttl=116 time=84.7 ms
```

* `route` show / manipulate the IP routing table

``` console
zold@Zold:~$ route
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
default         Zold.mshome.net 0.0.0.0         UG    0      0        0 eth0
172.27.160.0    0.0.0.0         255.255.240.0   U     0      0        0 eth0
```

* `arp` manipulate the system ARP cache

``` console
zold@Zold:~$ arp
Address                  HWtype  HWaddress           Flags Mask            Iface
Zold.mshome.net          ether   00:15:5d:51:39:07   C                     eth0
```

* `mtr` a combination of ping and traceroute commands. It is a network diagnostic tool that continuously sends packets showing ping time for each hop.

``` console
Zold (127.0.0.1)                                                        2022-06-16T11:05:37+0200 Keys:  Help   Display mode   Restart statistics   Order of fields   quit
                                                        Packets               Pings
 Host                                                 Loss%   Snt   Last   Avg  Best  Wrst StDev  1. localhost                                          0.0%    62    0.1   0.1   0.0   3.7   0.5 
```

* `dig www.google.com` querying DNS name servers.

``` console
zold@Zold:~$ dig www.google.com

; <<>> DiG 9.16.1-Ubuntu <<>> www.google.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 14077
;; flags: qr rd ad; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 0
;; WARNING: recursion requested but not available

;; QUESTION SECTION:
;www.google.com.                        IN      A

;; ANSWER SECTION:
www.google.com.         0       IN      A       142.251.37.36

;; Query time: 10 msec
;; SERVER: 172.27.160.1#53(172.27.160.1)
;; WHEN: Thu Jun 16 11:13:50 EET 2022
;; MSG SIZE  rcvd: 62
```

* `nslookup www.google.com` getting information from the DNS server.

``` console
zold@Zold:~$ nslookup www.google.com
Server:         172.27.160.1
Address:        172.27.160.1#53

Non-authoritative answer:
Name:   www.google.com
Address: 142.251.37.36
Name:   www.google.com
Address: 2a00:1450:4006:807::2004
```

[Next: SSH](./SSH.md)

[Prev: Processes](./Processes.md)
