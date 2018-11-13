# Configure VPN routing as initiator
The `cloud_vpn/configure_routing_initiator` function will configure the routing where
a VPN as initiator has been configured previously on Cisco ASA devices.
It is performed by calling the `cloud_vpn/configure_routing_initiator` task from the role.
The task will process variables needed for routing configuration and apply it to the device.

Below is an example to configure routing on a ASA device configured as initiator,
where the responder is Cisco ASA.

```
- hosts: cisco_asa

  tasks:
    - name: Configure initiator routing
      include_role:
        name: ansible-network.cisco_asa
        tasks_from: cloud_vpn/configure_routing_initiator
      vars:
        cloud_vpn_responder_provider: cisco_asa
        cloud_vpn_responder_cidr: 192.168.0.0/24
```

## Notes
None
