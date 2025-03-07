# Network Enumeration 🔍

## IP Configuration 🌐

The `ipconfig` command is used to display and manage network configurations on a Windows machine.

- **List all network interfaces:** 
  
  ```sh
  ipconfig
  ```

- **Display full configuration information:** 
  
  ```sh
  ipconfig /all
  ```

- **Release the IPv4 address for the specified adapter:** 
  
  ```sh
  ipconfig /release
  ```

- **Release the IPv6 address for the specified adapter:** 
  
  ```sh
  ipconfig /release6
  ```

- **Renew the IPv4 address for the specified adapter:** 
  
  ```sh
  ipconfig /renew
  ```

- **Renew the IPv6 address for the specified adapter:** 
  
  ```sh
  ipconfig /renew6
  ```

- **Display the contents of the DNS Resolver Cache:** 
  
  ```sh
  ipconfig /displaydns
  ```

- **Purge the DNS Resolver Cache:** 
  
  ```sh
  ipconfig /flushdns
  ```

- **Refresh all DHCP leases and register DNS names:** 
  
  ```sh
  ipconfig /registerdns
  ```

## Ping 📡

The `ping` command is used to check communication or connectivity between computers.

- **Check communication or connectivity of a computer:** 
  
  ```sh
  ping 192.168.1.6
  ```

- **Ping indefinitely:** ⏳
  
  ```sh
  ping 192.168.1.6 -t
  ```

- **Specify the number of echo requests to send:** 
  
  ```sh
  ping -n 1 192.168.1.6
  ```

- **Adjust the size of the ping packet:** 
  
  ```sh
  ping -n 1 -l 65500 192.168.1.6
  ```

## Traceroute 🛤️

The `tracert` command traces the path or route to a specified remote host.

- **Trace the route to the specified IP:** 🚦
  
  ```sh
  tracert 192.168.1.6
  ```

## Pathping 🚦

The `pathping` command combines the features of ping and tracert, providing information on network latency and packet loss.

- **Trace network latency and packet loss:** 📡
  
  ```sh
  pathping 8.8.8.8
  ```

## ARP (Address Resolution Protocol) 📜

The `arp` command is used to view and manage the ARP cache.

- **Display the ARP cache:** 🗂️
  
  ```sh
  arp -a
  ```

## NSLookup 🌍

The `nslookup` command allows users to look up DNS-related information.

- **Find the hostname associated with an IP address:** 🏠
  
  ```sh
  nslookup 192.168.1.33
  ```

- **Find the IP address associated with a domain name:** 🌐
  
  ```sh
  nslookup armour.com
  ```

## Route Table 🗺️

The `route` command is used to manipulate the IP routing table.

- **List the current routing table:** 📍
  
  ```sh
  route print
  ```

## Netstat 📊📡

The `netstat` command displays network statistics, connections, and routing tables.

- **Display active connections numerically:** 🔢
  
  ```sh
  netstat -n
  ```

- **Display all active connections and listening ports numerically:** 
  
  ```sh
  netstat -an
  ```

- **Display all active connections with process IDs:** 
  
  ```sh
  netstat -ano
  ```

- **Show TCP connections with process information:** 
  
  ```sh
  netstat -anop tcp
  ```

- **Show UDP connections with process information:** 
  
  ```sh
  netstat -anop udp
  ```

- **Display network connections with the associated executable:** 
  
  ```sh
  netstat -nob
  ```

- **Show all active connections, listening ports, and associated executables:** 
  
  ```sh
  netstat -anob
  ```
