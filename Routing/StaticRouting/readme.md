# Static Route Configuration

## Introduction
Static routing is a manual method of defining network paths, allowing administrators to control how traffic is forwarded within a network. Unlike dynamic routing protocols, static routes do not automatically adjust to network changes.

## Steps to Configure Static Routes

### 1. Access the Router
Connect to the router via SSH, Telnet, or the console:

```sh
ssh admin@router-ip
```

### 2. Enter Configuration Mode
For Cisco devices, enter privileged EXEC mode and then global configuration mode:

```sh
enable
configure terminal
```

### 3. Add a Static Route
Use the following command syntax:

```sh
ip route <destination-network> <subnet-mask> <next-hop-ip>
```

**Example:** To route traffic to the `192.168.2.0/24` network via the next-hop `192.168.1.1`, use:

```sh
ip route 192.168.2.0 255.255.255.0 192.168.1.1
```

### 4. Verify the Configuration
Check the routing table to confirm the static route is active:

```sh
show ip route
```

You should see an entry similar to:

```sh
S    192.168.2.0/24 [1/0] via 192.168.1.1
```

### 5. Save the Configuration
To make sure the route persists after a reboot, save the configuration:

```sh
write memory
```

or

```sh
copy running-config startup-config
```

## Troubleshooting

- **Ping Test:** Ensure connectivity using `ping`:
  
  ```sh
  ping 192.168.2.1
  ```
  
- **Check Interface Status:** Verify if the interface is up:
  
  ```sh
  show ip interface brief
  ```
  
- **Traceroute:** Identify where the packet is being dropped:
  
  ```sh
  traceroute 192.168.2.1
  ```

## Conclusion
Static routing is useful for small networks or specific paths requiring administrative control. However, in larger networks, dynamic routing protocols like OSPF or BGP are preferred for scalability.
