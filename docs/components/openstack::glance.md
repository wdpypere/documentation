
### Types

 - `/software/openstack/openstack_glance_store`
    - Description: 
    The Glance configuration options in the "glance_store" Section.
    From glance.api

    - `/software/openstack/openstack_glance_store/stores`
        - Description: List of enabled Glance stores.
    Register the storage backends to use for storing disk images
    as a comma separated list. The default stores enabled for
    storing disk images with Glance are "file" and "http"
        - Optional
        - Type: type_storagebackend
    - `/software/openstack/openstack_glance_store/default_store`
        - Description: The default scheme to use for storing images.
    Provide a string value representing the default scheme to use for
    storing images. If not set, Glance uses ``file`` as the default
    scheme to store images with the ``file`` store.
    NOTE: The value given for this configuration option must be a valid
    scheme for a store registered with the ``stores`` configuration
    option.
        - Optional
        - Type: string
        - Default value: file
    - `/software/openstack/openstack_glance_store/filesystem_store_datadir`
        - Description: Directory to which the filesystem backend store writes images.
    Upon start up, Glance creates the directory if it does not already
    exist and verifies write access to the user under which
    "glance-api" runs. If the write access is not available, a
    BadStoreConfiguration`` exception is raised and the filesystem
    store may not be available for adding new images.

    NOTE: This directory is used only when filesystem store is used as a
    storage backend. Either ``filesystem_store_datadir`` or
    filesystem_store_datadirs`` option must be specified in
    "glance-api.conf". If both options are specified, a
    BadStoreConfiguration will be raised and the filesystem store
    may not be available for adding new images
        - Optional
        - Type: type_directory
        - Default value: /var/lib/glance/images/
 - `/software/openstack/openstack_glance_config`
    - Description: 
    list of Glance configuration sections

    - `/software/openstack/openstack_glance_config/DEFAULT`
        - Optional
        - Type: openstack_DEFAULTS
    - `/software/openstack/openstack_glance_config/database`
        - Optional
        - Type: openstack_database
    - `/software/openstack/openstack_glance_config/keystone_authtoken`
        - Optional
        - Type: openstack_keystone_authtoken
    - `/software/openstack/openstack_glance_config/paste_deploy`
        - Optional
        - Type: openstack_keystone_paste_deploy
    - `/software/openstack/openstack_glance_config/glance_store`
        - Optional
        - Type: openstack_glance_store
