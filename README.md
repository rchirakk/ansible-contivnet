# ansible-contivnet
ansible role to install contiv netplugin

# Requirements
```
iptables
etcd
ovs
```

# Role variables
```
docker_version: docker version
netplugin_mode: docker or kubernetes
fwd_mode: bridge or routing
netmaster: yes or no
netplugin_ctrl_interface: control interface
netplugin_ctrl_ipaddress: ip address of control interface
netmaster_node: first netmaster node
netmaster_ipaddress: netmaster ip address
validate_certs: certs
contiv_network_version: plugin version
contiv_network_tar_file: tarfile location
contiv_network_src_file: url
contiv_network_dest_file: target file
```

# Example Playbook & inventory
```
- hosts: all
  become: true
  roles:
    - role: contivnet
    
```

```
[master]
192.168.33.10 netplugin_ctrl_interface=eth1 netplugin_vlan_interface=eth2 netmaster="yes"
[nodes]
192.168.33.11 netplugin_ctrl_interface=eth1 netplugin_vlan_interface=eth2  
192.168.33.12 netplugin_ctrl_interface=eth1 netplugin_vlan_interface=eth2  
```


# Testing