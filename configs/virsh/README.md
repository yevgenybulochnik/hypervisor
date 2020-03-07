## Virsh cheat sheet

### Create a bridge network
```
virsh net-define host-bridge.xml
virsh net-start host-bridge
virsh net-autostart host-bridge
virsh net-list --all
```
