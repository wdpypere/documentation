
### Types

 - `/software/openstack/openstack_component`
    - Description:
Type to define OpenStack services
Keystone, Nova, Neutron, etc

    - `/software/openstack/openstack_component/keystone`
        - Optional
        - Type: openstack_keystone_config
    - `/software/openstack/openstack_component/nova`
        - Optional
        - Type: openstack_nova_config
    - `/software/openstack/openstack_component/nova_compute`
        - Optional
        - Type: openstack_nova_compute_config
    - `/software/openstack/openstack_component/glance`
        - Optional
        - Type: openstack_glance_config
    - `/software/openstack/openstack_component/neutron`
        - Optional
        - Type: openstack_neutron_config
    - `/software/openstack/openstack_component/neutron_ml2`
        - Optional
        - Type: openstack_neutron_ml2_config
    - `/software/openstack/openstack_component/neutron_linuxbridge`
        - Optional
        - Type: openstack_neutron_linuxbridge_config
    - `/software/openstack/openstack_component/neutron_l3`
        - Optional
        - Type: openstack_neutron_l3_config
    - `/software/openstack/openstack_component/neutron_dhcp`
        - Optional
        - Type: openstack_neutron_dhcp_config
    - `/software/openstack/openstack_component/horizon`
        - Optional
        - Type: openstack_horizon_config
