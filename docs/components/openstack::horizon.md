
### Types

 - `/software/openstack/openstack_horizon_caches`
    - Description: 
    The Horizon configuration options in "caches" Section.

    - `/software/openstack/openstack_horizon_caches/backend`
        - Description: We recommend you use memcached for development; otherwise after every reload
     of the django development server, you will have to login again
        - Optional
        - Type: string
        - Default value: django.core.cache.backends.memcached.MemcachedCache
    - `/software/openstack/openstack_horizon_caches/location`
        - Description: location format <fqdn>:<port>
        - Optional
        - Type: type_hostport
 - `/software/openstack/openstack_horizon_api_versions`
    - Description: 
    The Horizon api versions section.
    Overrides for OpenStack API versions. Use this setting to force the
    OpenStack dashboard to use a specific API version for a given service API.
    Versions specified here should be integers or floats, not strings.
    NOTE: The version should be formatted as it appears in the URL for the
    service API. For example, The identity service APIs have inconsistent
    use of the decimal point, so valid options would be 2.0 or 3.
    Minimum compute version to get the instance locked status is 2.9.

    - `/software/openstack/openstack_horizon_api_versions/identity`
        - Optional
        - Type: long
        - Range: 1..
        - Default value: 3
    - `/software/openstack/openstack_horizon_api_versions/image`
        - Optional
        - Type: long
        - Range: 1..
        - Default value: 2
    - `/software/openstack/openstack_horizon_api_versions/volume`
        - Optional
        - Type: long
        - Range: 1..
        - Default value: 2
 - `/software/openstack/openstack_horizon_neutron_network`
    - Description: 
    The Horizon "OPENSTACK_NEUTRON_NETWORK" settings can be used to enable optional
    services provided by neutron. Options currently available are load
    balancer service, security groups, quotas, VPN service.

    - `/software/openstack/openstack_horizon_neutron_network/enable_router`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_neutron_network/enable_quotas`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_neutron_network/enable_ipv6`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_neutron_network/enable_distributed_router`
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/openstack/openstack_horizon_neutron_network/enable_ha_router`
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/openstack/openstack_horizon_neutron_network/enable_lb`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_neutron_network/enable_firewall`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_neutron_network/enable_vpn`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_neutron_network/enable_fip_topology_check`
        - Optional
        - Type: boolean
        - Default value: true
 - `/software/openstack/openstack_horizon_keystone_backend`
    - Description: 
    The OPENSTACK_KEYSTONE_BACKEND settings can be used to identify the
    capabilities of the auth backend for Keystone.
    If Keystone has been configured to use LDAP as the auth backend then set
    can_edit_user to False and name to 'ldap'.
    TODO(tres): Remove these once Keystone has an API to identify auth backend.

    - `/software/openstack/openstack_horizon_keystone_backend/name`
        - Optional
        - Type: string
        - Default value: native
    - `/software/openstack/openstack_horizon_keystone_backend/can_edit_user`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_keystone_backend/can_edit_group`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_keystone_backend/can_edit_project`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_keystone_backend/can_edit_domain`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_keystone_backend/can_edit_role`
        - Optional
        - Type: boolean
        - Default value: true
 - `/software/openstack/openstack_horizon_hypervisor_features`
    - Description: 
    The Xen Hypervisor has the ability to set the mount point for volumes
    attached to instances (other Hypervisors currently do not). Setting
    can_set_mount_point to True will add the option to set the mount point
    from the UI.

    - `/software/openstack/openstack_horizon_hypervisor_features/can_set_mount_point`
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/openstack/openstack_horizon_hypervisor_features/can_set_password`
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/openstack/openstack_horizon_hypervisor_features/requires_keypair`
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/openstack/openstack_horizon_hypervisor_features/enable_quotas`
        - Optional
        - Type: boolean
        - Default value: true
 - `/software/openstack/openstack_horizon_cinder_features`
    - Description: 
    The OPENSTACK_CINDER_FEATURES settings can be used to enable optional
    services provided by cinder that is not exposed by its extension API.

    - `/software/openstack/openstack_horizon_cinder_features/enable_backup`
        - Optional
        - Type: boolean
        - Default value: false
 - `/software/openstack/openstack_horizon_heat_stack`
    - Description: 
    The OPENSTACK_HEAT_STACK settings can be used to disable password
    field required while launching the stack.

    - `/software/openstack/openstack_horizon_heat_stack/enable_user_pass`
        - Optional
        - Type: boolean
        - Default value: true
 - `/software/openstack/openstack_horizon_image_custom_titles`
    - Description: 
    The IMAGE_CUSTOM_PROPERTY_TITLES settings is used to customize the titles for
    image custom property attributes that appear on image detail pages.

    - `/software/openstack/openstack_horizon_image_custom_titles/architecture`
        - Optional
        - Type: string
        - Default value: Architecture
    - `/software/openstack/openstack_horizon_image_custom_titles/kernel_id`
        - Optional
        - Type: string
        - Default value: Kernel ID
    - `/software/openstack/openstack_horizon_image_custom_titles/ramdisk_id`
        - Optional
        - Type: string
        - Default value: Ramdisk ID
    - `/software/openstack/openstack_horizon_image_custom_titles/image_state`
        - Optional
        - Type: string
        - Default value: Euca2ools state
    - `/software/openstack/openstack_horizon_image_custom_titles/project_id`
        - Optional
        - Type: string
        - Default value: Project ID
    - `/software/openstack/openstack_horizon_image_custom_titles/image_type`
        - Optional
        - Type: string
        - Default value: Image Type
 - `/software/openstack/openstack_horizon_logging_handlers`
    - Description: 
    Dashboard handlers logging levels.

    - `/software/openstack/openstack_horizon_logging_handlers/level`
        - Optional
        - Type: string
        - Default value: INFO
    - `/software/openstack/openstack_horizon_logging_handlers/class`
        - Optional
        - Type: string
        - Default value: logging.StreamHandler
    - `/software/openstack/openstack_horizon_logging_handlers/formatter`
        - Optional
        - Type: string
        - Default value: operation
 - `/software/openstack/openstack_horizon_logging_loggers`
    - Description: 
    Dashboard django loggers debug levels

    - `/software/openstack/openstack_horizon_logging_loggers/handlers`
        - Optional
        - Type: string
        - Default value: console
    - `/software/openstack/openstack_horizon_logging_loggers/level`
        - Optional
        - Type: string
        - Default value: DEBUG
    - `/software/openstack/openstack_horizon_logging_loggers/propagate`
        - Optional
        - Type: boolean
        - Default value: false
 - `/software/openstack/openstack_horizon_logging_formatters`
    - Description: 
    Dashboard django logger formatters

    - `/software/openstack/openstack_horizon_logging_formatters/format`
        - Description: The format of "%(message)s" is defined by
    OPERATION_LOG_OPTIONS['format']
        - Optional
        - Type: string
        - Default value: %(asctime)s %(message)s
 - `/software/openstack/openstack_horizon_logging`
    - Description: 
    Horizon django logging options.
    Logging from django.db.backends is VERY verbose, send to null
    by default.

    - `/software/openstack/openstack_horizon_logging/version`
        - Optional
        - Type: long
        - Range: 1..
        - Default value: 1
    - `/software/openstack/openstack_horizon_logging/disable_existing_loggers`
        - Description: When set to True this will disable all logging except
    for loggers specified in this configuration dictionary. Note that
    if nothing is specified here and disable_existing_loggers is True,
    django.db.backends will still log unless it is disabled explicitly
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/openstack/openstack_horizon_logging/handlers`
        - Optional
        - Type: openstack_horizon_logging_handlers
    - `/software/openstack/openstack_horizon_logging/loggers`
        - Optional
        - Type: openstack_horizon_logging_loggers
    - `/software/openstack/openstack_horizon_logging/formatters`
        - Optional
        - Type: openstack_horizon_logging_formatters
 - `/software/openstack/openstack_horizon_allowed_subnet`
    - Description: 
    Dictionary used to restrict user private subnet cidr range.
    An empty list means that user input will not be restricted
    for a corresponding IP version. By default, there is
    no restriction for IPv4 or IPv6. To restrict
    user private subnet cidr range set ALLOWED_PRIVATE_SUBNET_CIDR
    to something like:
        'ipv4': ['10.0.0.0/8', '192.168.0.0/16'],
        'ipv6': ['fc00::/7'],

    - `/software/openstack/openstack_horizon_allowed_subnet/ipv4`
        - Optional
        - Type: type_ip
    - `/software/openstack/openstack_horizon_allowed_subnet/ipv6`
        - Optional
        - Type: type_ip
 - `/software/openstack/openstack_horizon_security_group`
    - Description: 
    "direction" should not be specified for all_tcp, udp or icmp.

    - `/software/openstack/openstack_horizon_security_group/name`
        - Optional
        - Type: string
    - `/software/openstack/openstack_horizon_security_group/ip_protocol`
        - Optional
        - Type: string
        - Default value: tcp
    - `/software/openstack/openstack_horizon_security_group/from_port`
        - Optional
        - Type: long
        - Range: -1..65535
    - `/software/openstack/openstack_horizon_security_group/to_port`
        - Optional
        - Type: long
        - Range: -1..65535
 - `/software/openstack/openstack_horizon_config`
    - Description: 
    list of Horizon service configuration sections

    - `/software/openstack/openstack_horizon_config/debug`
        - Description: Set Horizon debug mode
        - Optional
        - Type: boolean
        - Default value: false
    - `/software/openstack/openstack_horizon_config/webroot`
        - Description: WEBROOT is the location relative to Webserver root
    should end with a slash
        - Optional
        - Type: string
        - Default value: /dashboard/
    - `/software/openstack/openstack_horizon_config/allowed_hosts`
        - Description: If horizon is running in production (DEBUG is False), set this
    with the list of host/domain names that the application can serve.
    For more information see:
    https://docs.djangoproject.com/en/dev/ref/settings/#allowed-hosts
        - Optional
        - Type: string
    - `/software/openstack/openstack_horizon_config/session_engine`
        - Description: Horizon uses Djangos sessions framework for handling session data.
    There are numerous session backends available, which are selected 
    through the "SESSION_ENGINE" setting
        - Optional
        - Type: string
        - Default value: django.contrib.sessions.backends.cache
    - `/software/openstack/openstack_horizon_config/email_backend`
        - Description: Send email to the console by default
        - Optional
        - Type: string
        - Default value: django.core.mail.backends.console.EmailBackend
    - `/software/openstack/openstack_horizon_config/caches`
        - Description: External caching using an application such as memcached offers persistence
    and shared storage, and can be very useful for small-scale deployment 
    and/or development
        - Optional
        - Type: openstack_horizon_caches
    - `/software/openstack/openstack_horizon_config/openstack_keystone_url`
        - Optional
        - Type: type_absoluteURI
    - `/software/openstack/openstack_horizon_config/openstack_keystone_default_role`
        - Description: Set this to True if running on a multi-domain model. When this is enabled, it
    will require the user to enter the Domain name in addition to the username
    for login
        - Optional
        - Type: string
        - Default value: user
    - `/software/openstack/openstack_horizon_config/openstack_keystone_multidomain_support`
        - Optional
        - Type: boolean
        - Default value: true
    - `/software/openstack/openstack_horizon_config/openstack_keystone_backend`
        - Optional
        - Type: openstack_horizon_keystone_backend
    - `/software/openstack/openstack_horizon_config/openstack_api_versions`
        - Optional
        - Type: openstack_horizon_api_versions
    - `/software/openstack/openstack_horizon_config/openstack_hypervisor_features`
        - Optional
        - Type: openstack_horizon_hypervisor_features
    - `/software/openstack/openstack_horizon_config/openstack_cinder_features`
        - Optional
        - Type: openstack_horizon_cinder_features
    - `/software/openstack/openstack_horizon_config/openstack_heat_stack`
        - Optional
        - Type: openstack_horizon_heat_stack
    - `/software/openstack/openstack_horizon_config/image_custom_property_titles`
        - Optional
        - Type: openstack_horizon_image_custom_titles
    - `/software/openstack/openstack_horizon_config/image_reserved_custom_properties`
        - Description: The IMAGE_RESERVED_CUSTOM_PROPERTIES setting is used to specify which image
    custom properties should not be displayed in the Image Custom Properties
    table
        - Optional
        - Type: string
    - `/software/openstack/openstack_horizon_config/api_result_limit`
        - Description: The number of objects (Swift containers/objects or images) to display
    on a single page before providing a paging element (a "more" link)
    to paginate results
        - Optional
        - Type: long
        - Range: 1..
        - Default value: 1000
    - `/software/openstack/openstack_horizon_config/api_result_page_size`
        - Optional
        - Type: long
        - Range: 1..
        - Default value: 20
    - `/software/openstack/openstack_horizon_config/swift_file_transfer_chunk_size`
        - Description: The size of chunk in bytes for downloading objects from Swift
        - Optional
        - Type: long
        - Range: 1..
        - Default value: 524288
    - `/software/openstack/openstack_horizon_config/instance_log_length`
        - Description: The default number of lines displayed for instance console log
        - Optional
        - Type: long
        - Range: 1..
        - Default value: 35
    - `/software/openstack/openstack_horizon_config/local_path`
        - Optional
        - Type: type_directory
        - Default value: /tmp
    - `/software/openstack/openstack_horizon_config/secret_key`
        - Description: You can either set it to a specific value or you can let horizon generate a
    default secret key that is unique on this machine, e.i. regardless of the
    amount of Python WSGI workers (if used behind Apache+mod_wsgi): However,
    there may be situations where you would want to set this explicitly, e.g.
    when multiple dashboard instances are distributed on different machines
    (usually behind a load-balancer). Either you have to make sure that a session
    gets all requests routed to the same dashboard instance or you set the same
    SECRET_KEY for all of them
        - Optional
        - Type: string
    - `/software/openstack/openstack_horizon_config/openstack_keystone_default_domain`
        - Description: Overrides the default domain used when running on single-domain model
    with Keystone V3. All entities will be created in the default domain.
    NOTE: This value must be the name of the default domain, NOT the ID.
    Also, you will most likely have a value in the keystone policy file like this
    "cloud_admin": "rule:admin_required and domain_id:<your domain id>"
    This value must be the name of the domain whose ID is specified there
        - Optional
        - Type: string
        - Default value: Default
    - `/software/openstack/openstack_horizon_config/openstack_keystone_default_role`
        - Description: Configure the default role for users that you create via the dashboard
        - Optional
        - Type: string
        - Default value: user
    - `/software/openstack/openstack_horizon_config/openstack_neutron_network`
        - Optional
        - Type: openstack_horizon_neutron_network
    - `/software/openstack/openstack_horizon_config/time_zone`
        - Description: The timezone of the server. This should correspond with the timezone
    of your entire OpenStack installation, and hopefully be in UTC.
    Example: "Europe/Brussels"
        - Optional
        - Type: string
    - `/software/openstack/openstack_horizon_config/policy_files_path`
        - Description: Path to directory containing policy.json files
        - Optional
        - Type: type_directory
        - Default value: /etc/openstack-dashboard
    - `/software/openstack/openstack_horizon_config/logging`
        - Optional
        - Type: openstack_horizon_logging
    - `/software/openstack/openstack_horizon_config/rest_api_required_settings`
        - Description: AngularJS requires some settings to be made available to
    the client side. Some settings are required by in-tree / built-in horizon
    features. These settings must be added to REST_API_REQUIRED_SETTINGS in the
    form of ['SETTING_1','SETTING_2'], etc.
    You may remove settings from this list for security purposes, but do so at
    the risk of breaking a built-in horizon feature. These settings are required
    for horizon to function properly. Only remove them if you know what you
    are doing. These settings may in the future be moved to be defined within
    the enabled panel configuration.
    You should not add settings to this list for out of tree extensions
        - Optional
        - Type: string
    - `/software/openstack/openstack_horizon_config/allowed_private_subnet_cidr`
        - Optional
        - Type: openstack_horizon_allowed_subnet
    - `/software/openstack/openstack_horizon_config/security_group_files`
        - Optional
        - Type: openstack_horizon_security_group
