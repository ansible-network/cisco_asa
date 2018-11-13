# Configure VPN as initiator
The `cloud_vpn/configure_vpn_initiator` function will configure IPSEC VPN as initiator
on Cisco ASA devices.
It is performed by calling the `cloud_vpn/configure_vpn_initiator` task from the role.
The task will process variables needed for VPN configuration and apply it to the device.

Below is an example to configure an IPSEC VPN as initiator on ASA device, where
the responder is Cisco ASA:

```
- hosts: cisco_asa

  tasks:
    - name: Configure IPSEC VPN as initiator
      include_role:
        name: ansible-network.cisco_asa
        tasks_from: cloud_vpn/configure_vpn_initiator
      vars:
        cloud_vpn_name: myvpn
        cloud_vpn_psk: mypsksecret
        cloud_vpn_initiator_provider: asa
        cloud_vpn_initiator_outside_interface: Management
        cloud_vpn_initiator_tunnel_ip: 169.254.56.25
        cloud_vpn_responder_provider: asa
        cloud_vpn_responder_public_ip: 18.191.132.220
        cloud_vpn_responder_tunnel_ip: 169.254.56.26
```

## Notes
None
