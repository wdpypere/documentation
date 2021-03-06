
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
        - Type: absolute_file_path
        - Default value: /var/lib/glance/images
    - `/software/openstack/openstack_glance_store/rbd_store_pool`
        - Description: This option is specific to the RBD storage backend.
    Default: rbd
    Sets the RADOS pool in which images are stored
        - Optional
        - Type: string
        - Default value: images
    - `/software/openstack/openstack_glance_store/rbd_store_chunk_size`
        - Description: This option is specific to the RBD storage backend.
    Default: 4
    Images will be chunked into objects of this size (in megabytes).
    For best performance, this should be a power of two
        - Optional
        - Type: long
        - Range: 1..
    - `/software/openstack/openstack_glance_store/rados_connect_timeout`
        - Description: This option is specific to the RBD storage backend.
    Default: 0
    Prevents glance-api hangups during the connection to RBD.
    Sets the time to wait (in seconds) for glance-api before closing the connection.
    Setting rados_connect_timeout<=0 means no timeout
        - Optional
        - Type: long
    - `/software/openstack/openstack_glance_store/rbd_store_ceph_conf`
        - Description: This option is specific to the RBD storage backend.
    Default: /etc/ceph/ceph.conf, ~/.ceph/config, and ./ceph.conf
    Sets the Ceph configuration file to use
        - Optional
        - Type: absolute_file_path
        - Default value: /etc/ceph/ceph.conf
    - `/software/openstack/openstack_glance_store/rbd_store_user`
        - Description: This option is specific to the RBD storage backend.
    Default: admin
    Sets the RADOS user to authenticate as.
    This is only needed when RADOS authentication is enabled
        - Optional
        - Type: string
        - Default value: images
 - `/software/openstack/openstack_glance_service_config`
    - Description:
    list of Glance configuration sections

    - `/software/openstack/openstack_glance_service_config/DEFAULT`
        - Optional
        - Type: openstack_DEFAULTS
    - `/software/openstack/openstack_glance_service_config/database`
        - Optional
        - Type: openstack_database
    - `/software/openstack/openstack_glance_service_config/keystone_authtoken`
        - Optional
        - Type: openstack_keystone_authtoken
    - `/software/openstack/openstack_glance_service_config/paste_deploy`
        - Optional
        - Type: openstack_keystone_paste_deploy
    - `/software/openstack/openstack_glance_service_config/glance_store`
        - Optional
        - Type: openstack_glance_store
 - `/software/openstack/openstack_glance_config`
    - Description:
    list of Glance service configuration sections

    - `/software/openstack/openstack_glance_config/service`
        - Optional
        - Type: openstack_glance_service_config
    - `/software/openstack/openstack_glance_config/registry`
        - Optional
        - Type: openstack_glance_service_config
