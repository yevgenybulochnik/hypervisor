## Virsh cheat sheet

### Create a bridge network

#### Example netplan setup, static ip + bridge to home network
```
network:
  version: 2
  renderer: networkd
  ethernets:
    eno1:
      dhcp4: false
  bridges:
    br0:
      dhcp4: false
      interfaces: [eno1]
      addresses: [192.168.1.5/24]
      gateway4: 192.168.1.1
      nameservers:
        addresses: [192.168.1.1,8.8.8.8]
```

#### Virsh network commands
```
virsh net-define host-bridge.xml
virsh net-start host-bridge
virsh net-autostart host-bridge
virsh net-list --all
```
