
### Types

 - `/software/opennebula/structure_aii_opennebula`
    - `/software/opennebula/structure_aii_opennebula/module`
        - Optional
        - Type: string
    - `/software/opennebula/structure_aii_opennebula/image`
        - Description: force create image from scratch, also stop/delete vm.
    VM images are not updated, if you want to resize or modify an available
    image from scratch use remove hook first.
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/opennebula/structure_aii_opennebula/template`
        - Description: force (re)create template, also stop/delete vm
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/opennebula/structure_aii_opennebula/vm`
        - Description: instantiate template (i.e. make vm)
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/opennebula/structure_aii_opennebula/onhold`
        - Description: vm is placed onhold, if false the VM execution is scheduled asap
        - Optional
        - Type: boolean
        - Default value: true
 - `/software/opennebula/opennebula_vmtemplate_vnet`
 - `/software/opennebula/opennebula_vmtemplate_datastore`
 - `/software/opennebula/valid_interface_ignoremac`
    - Description: 
Type that checks if the network interface is available from the quattor tree

 - `/software/opennebula/opennebula_ignoremac`
    - Description: 
Type that sets which net interfaces/MACs
will not include MAC values within ONE templates

    - `/software/opennebula/opennebula_ignoremac/macaddr`
        - Optional
        - Type: type_hwaddr
    - `/software/opennebula/opennebula_ignoremac/interface`
        - Optional
        - Type: valid_interface_ignoremac
 - `/software/opennebula/opennebula_permissions`
    - Description: 
Type that changes resources owner/group permissions.
By default opennebula-aii generates all the resources as oneadmin owner/group.
  owner: OpenNebula user id or user name
  group: OpenNebula group id or username
  mode:  Octal notation, e.g. 0600

    - `/software/opennebula/opennebula_permissions/owner`
        - Optional
        - Type: string
    - `/software/opennebula/opennebula_permissions/group`
        - Optional
        - Type: string
    - `/software/opennebula/opennebula_permissions/mode`
        - Optional
        - Type: long
 - `/software/opennebula/opennebula_vmtemplate_pci`
    - Description: 
It is possible to discover PCI devices in the hosts
and assign them to Virtual Machines for the KVM host.
I/O MMU and SR-IOV must be supported and enabled by the host OS and BIOS.
More than one PCI option can be added to attach more than one PCI device to the VM.
The device can be also specified without all the type values.
PCI values must be hexadecimal (0xhex)
If the PCI values are not found in any host the VM is queued waiting for the
required resouces.

"onehost show <host>" command gives us the list
of PCI devices and "vendor", "device" and "class" values within PCI DEVICES section
as example:

VM ADDR    TYPE           NAME
   06:00.1 15b3:1002:0c06 MT25400 Family [ConnectX-2 Virtual Function]

  VM: The VM ID using that specific device. Empty if no VMs are using that device.
  ADDR: PCI Address.
  TYPE: Values describing the device. These are VENDOR:DEVICE:CLASS.
        These values are used when selecting a PCI device do to passthrough.
  NAME: Name of the PCI device.

In this case to request this IB device we should set:
  vendor: 0x15b3
  device: 0x1002
  class:  0x0c06

For more info:
http://docs.opennebula.org/5.0/deployment/open_cloud_host_setup/pci_passthrough.html

    - `/software/opennebula/opennebula_vmtemplate_pci/vendor`
        - Description: first value from onehost TYPE section
        - Optional
        - Type: long
    - `/software/opennebula/opennebula_vmtemplate_pci/device`
        - Description: second value from onehost TYPE section
        - Optional
        - Type: long
    - `/software/opennebula/opennebula_vmtemplate_pci/class`
        - Description: third value from onehost TYPE section
        - Optional
        - Type: long
 - `/software/opennebula/opennebula_placements`
    - Description: 
Type that sets placement constraints and preferences for the VM, valid for all hosts
More info: http://docs.opennebula.org/5.0/operation/references/template.html#placement-section

    - `/software/opennebula/opennebula_placements/sched_requirements`
        - Description: Boolean expression that rules out provisioning hosts from list of machines
    suitable to run this VM.
        - Optional
        - Type: string
    - `/software/opennebula/opennebula_placements/sched_rank`
        - Description: This field sets which attribute will be used to sort the suitable hosts for this VM.
    Basically, it defines which hosts are more suitable than others.
        - Optional
        - Type: string
    - `/software/opennebula/opennebula_placements/sched_ds_requirements`
        - Description: Boolean expression that rules out entries from the pool of datastores suitable
    to run this VM.
        - Optional
        - Type: string
    - `/software/opennebula/opennebula_placements/sched_ds_rank`
        - Description: States which attribute will be used to sort the suitable datastores for this VM.
    Basically, it defines which datastores are more suitable than others.
        - Optional
        - Type: string
 - `/software/opennebula/opennebula_vmtemplate`
    - `/software/opennebula/opennebula_vmtemplate/vnet`
        - Description: Set the VNETs opennebula/vnet (bridges) required by each VM network interface
        - Optional
        - Type: opennebula_vmtemplate_vnet
    - `/software/opennebula/opennebula_vmtemplate/datastore`
        - Description: Set the OpenNebula opennebula/datastore name for each vdx
        - Optional
        - Type: opennebula_vmtemplate_datastore
    - `/software/opennebula/opennebula_vmtemplate/ignoremac`
        - Description: Set ignoremac tree to avoid to include MAC values within AR/VM templates
        - Optional
        - Type: opennebula_ignoremac
    - `/software/opennebula/opennebula_vmtemplate/graphics`
        - Description: Set graphics to export VM graphical display (VNC is used by default)
        - Optional
        - Type: string
        - Default value: VNC
    - `/software/opennebula/opennebula_vmtemplate/diskcache`
        - Description: Select the cache mechanism for your disks. (by default is set to none)
        - Optional
        - Type: string
    - `/software/opennebula/opennebula_vmtemplate/diskdriver`
        - Description: specific image mapping driver. qcow2 is not supported by Ceph storage backends
        - Optional
        - Type: string
    - `/software/opennebula/opennebula_vmtemplate/permissions`
        - Optional
        - Type: opennebula_permissions
    - `/software/opennebula/opennebula_vmtemplate/pci`
        - Description: Set pci list values to enable PCI Passthrough.
    PCI passthrough section is also generated based on /hardware/cards/<card_type>/<interface>/pci values.
        - Optional
        - Type: opennebula_vmtemplate_pci
    - `/software/opennebula/opennebula_vmtemplate/labels`
        - Description: labels is a list of strings to group the VMs under a given name and filter them
    in the admin and cloud views. It is also possible to include in the list
    sub-labels using a common slash: list("Name", "Name/SubName")
    This feature is available since OpenNebula 5.x, below this version the change
    does not take effect.
        - Optional
        - Type: string
    - `/software/opennebula/opennebula_vmtemplate/placements`
        - Optional
        - Type: opennebula_placements
    - `/software/opennebula/opennebula_vmtemplate/memorybacking`
        - Description: The optional memoryBacking element may contain several elements that influence
    how virtual memory pages are backed by host pages.
    hugepages: This tells the hypervisor that the guest should have its memory
    allocated using hugepages instead of the normal native page size.
    nosharepages: Instructs hypervisor to disable shared pages
    (memory merge, KSM) for this domain.
    locked: When set and supported by the hypervisor, memory pages belonging to the domain
    will be locked in hosts memory and the host will not be allowed to swap them out,
    which might be required for some workloads such as real-time. For QEMU/KVM guests,
    the memory used by the QEMU process itself will be locked too: unlike guest memory,
    this is an amount libvirt has no way of figuring out in advance, so it has to remove
    the limit on locked memory altogether. Thus, enabling this option opens up to a
    potential security risk: the host will be unable to reclaim the locked memory back
    from the guest when its running out of memory, which means a malicious guest allocating
    large amounts of locked memory could cause a denial-of-service attach on the host.
        - Optional
        - Type: string

### Functions

 - validate_aii_opennebula_hooks
    - Description: 
Function to validate all aii_opennebula hooks

 - is_consistent_memorybacking
