**VLAN Configuration Guide**

### **Introduction**
VLAN (Virtual Local Area Network) is a technology that allows network segmentation at Layer 2, improving security and efficiency. This guide provides a structured approach to configuring VLANs on a switch, including assigning ports as access or trunk.

### **Understanding Access and Trunk Ports**
- **Access Port**: Used for end devices such as computers, printers, and IP phones. It carries traffic for a single VLAN only.
- **Trunk Port**: Used to connect switches or a switch to a router. It carries traffic for multiple VLANs using VLAN tagging (802.1Q).
- **Native VLAN**: The VLAN that is untagged on a trunk port. By default, it is VLAN 1, but it can be changed for security reasons. It is used for management and can be a potential security risk if not properly configured.

### **Step-by-Step VLAN Configuration**
#### **Step 1: Creating VLANs**
1. Enter privileged EXEC mode:
   ```
   enable
   ```
2. Enter global configuration mode:
   ```
   configure terminal
   ```
3. Create VLANs:
   ```
   vlan 10
   name Sales
   exit
   vlan 20
   name IT
   exit
   vlan 30
   name HR
   exit
   vlan 99
   name Native_VLAN
   exit
   ```

#### **Step 2: Assigning Ports to VLANs (Access Mode)**
1. Select an interface for end devices:
   ```
   interface FastEthernet0/1
   switchport mode access
   switchport access vlan 10
   exit
   interface FastEthernet0/2
   switchport mode access
   switchport access vlan 20
   exit
   ```
2. Repeat for other ports as needed.

#### **Step 3: Configuring Trunk Ports**
1. Select an interface for trunk connection (e.g., switch-to-switch or switch-to-router):
   ```
   interface FastEthernet0/24
   switchport mode trunk
   switchport trunk allowed vlan 10,20,30
   exit
   ```
2. Configure the native VLAN on the trunk:
   ```
   interface FastEthernet0/24
   switchport trunk native vlan 99
   exit
   ```
3. Verify trunk configuration:
   ```
   show interfaces trunk
   ```

#### **Step 4: Configuring Native VLAN on an Access Port**
1. Assign a specific port for native VLAN management:
   ```
   interface FastEthernet0/10
   switchport mode access
   switchport access vlan 99
   exit
   ```
2. Verify the configuration:
   ```
   show vlan brief
   ```
   ```
   show interfaces FastEthernet0/10 switchport
   ```

#### **Step 5: Verifying VLAN Configuration**
1. Check VLAN assignment:
   ```
   show vlan brief
   ```
2. Verify interface mode:
   ```
   show interfaces FastEthernet0/1 switchport
   ```
3. Verify native VLAN configuration:
   ```
   show interfaces FastEthernet0/24 trunk
   ```

### **Conclusion**
By correctly configuring VLANs with access and trunk ports, network segmentation is achieved, improving security and traffic management. Proper trunking ensures VLAN traffic is carried between switches and routers efficiently. Configuring the native VLAN correctly enhances security and prevents VLAN hopping attacks.


