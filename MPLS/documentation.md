# MPLS and MP-BGP VPN Configuration Labs

## Overview

This folder contains labs and configurations related to **MPLS (Multiprotocol Label Switching)** and **MP-BGP (Multiprotocol Border Gateway Protocol)** used for setting up **VPN tunnels** in an MPLS network. These labs will guide you through the steps needed to configure and test MPLS and MP-BGP in order to create a functional **Layer 3 VPN** infrastructure. 

By utilizing MPLS with MP-BGP, you will learn how to establish **VPNv4** routes, separate customer traffic using **VRF (Virtual Routing and Forwarding)**, and ensure secure communication across an MPLS backbone.

## Labs Included

The following configurations and concepts are covered in the labs:

1. **OSPF Configuration in the ISP Cloud**  
   Configuring OSPF as a routing protocol for the ISP backbone, enabling MPLS label distribution with OSPF.

2. **MPLS Configuration on ISP Routers**  
   Enabling MPLS on routers in the ISP core and establishing label distribution protocol (LDP) to allow MPLS packet forwarding.

3. **MP-BGP Configuration for VPNv4**  
   Setting up **Multiprotocol BGP (MP-BGP)** to exchange **VPNv4** routes between Provider Edge (PE) routers, even in the absence of direct connections.

4. **VRF Configuration on Provider Edge Routers**  
   Setting up VRF instances on PE routers to separate customer routing tables and ensure isolated traffic flows between customers.

5. **Redistribution of Static Routes into BGP**  
   Configuring the redistribution of static routes into the BGP process for VPN routing.

6. **OSPF and BGP Redistribution in VRF Context**  
   Exploring how to redistribute OSPF and BGP routes into each other for proper route exchange and routing between customer sites.

7. **Verifying VPN Configuration**  
   Methods for verifying the proper setup of VPN tunnels and the propagation of routes across the MPLS network.

## Objective

- **Establish VPN Connectivity**: You will learn to create VPN tunnels using MPLS and MP-BGP to facilitate secure and isolated communication between customer sites over the ISP's MPLS backbone.
  
- **Implement VRF to Separate Customer Traffic**: By configuring VRFs, each customer’s traffic is isolated in separate routing tables, providing secure and efficient routing for different customers on the same network.

- **Enable BGP to Exchange VPN Routes**: MP-BGP will be used to exchange VPNv4 routes across the MPLS network, allowing the service provider to offer end-to-end connectivity between customer sites.

## Requirements

- Cisco Routers (or Cisco Packet Tracer/Simulator) with MPLS and BGP support.
- Basic knowledge of networking concepts, including routing protocols like OSPF and BGP, as well as MPLS and VPN technologies.
- Access to a command-line interface (CLI) to configure devices.

## How to Use

Each lab is structured as a step-by-step guide to help you configure various aspects of MPLS and MP-BGP VPN. You can follow the steps for each specific task (such as configuring OSPF, enabling MPLS, or setting up MP-BGP) in the appropriate sequence.

### Example Steps

1. **OSPF Configuration**  
   Configure OSPF routing between the ISP routers and enable MPLS support.
   
2. **MP-BGP Setup**  
   Establish MP-BGP peering between Provider Edge routers (R1 and R3), enabling the exchange of VPNv4 routes.
   
3. **VRF Setup**  
   Configure VRF on Provider Edge routers to isolate customer routing.

4. **Verify VPN Operation**  
   Use commands like `show ip route vrf <vrf_name>` or `show bgp vpnv4 unicast` to check the BGP table for VPN routes.

For each lab, the configuration files and the necessary commands are provided in the respective folders.

## Conclusion

By completing these labs, you will gain a practical understanding of how MPLS and MP-BGP work together to create secure, scalable VPNs over an MPLS backbone, ensuring that customer traffic is properly routed and isolated.

---

**Note:** For detailed explanations and configuration examples, please refer to the individual lab files in this folder.
