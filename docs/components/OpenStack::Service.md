
####  Functions

- get\_flavour

    Determine the name of the flavour based on type and tree and log/reporter instance
    (eg name=keystone for type=identity)

- get\_fqdn

    Get `fqdn` of the host using host profile `config` instance.

- get\_service

    Service factory: loads custom subclasses when one exists
    Same args as \_initialize

- run\_service

    Convenience function around get\_service, includes basic reporting

#### Methods

- \_init\_attrs

    Arguments:

    - type: eg identity
    - config: full profile config instance
    - log: reporter instance
    - prefix: the component prefix (for subclassing)
    - client: Net::OpenStack::Client instance

- \_initialize

    Initialisation using `_init_attrs`, `_attrs` and `_daemons`.

- \_daemons

    Method to customise the `daemons` attribute during `_initialize`.

- \_set\_elpath

    Return main element path

- \_attrs

    Add/set/modify more attributes
    Conviennce method for inheritance
    instead of using SUPER
        my $res = $self->SUPER::method(@\_);

- \_render

    Returns CCM::TextRedner instance

- \_file\_opts

    Return hashref with filewriter options for `service`
    (incl owned by that service user)

- \_write\_config\_file

    Write the config file with name `filename` and `element` instance.

- \_write\_config\_files

    Write multiple config files based on entries in the `tree` attribute.
    Filename is based on mapping in the `filename` attribute;
    a mapping which daemon(s) to start when the file is modified can
    be provided via the `daemon_map` attribute.

- write\_config\_file

    Write the config files (when `filenames` attribute is a hashref) or single file otherwise.

- \_read\_ceph\_keyring

    Read Ceph pool key file from `keyring`.

- \_libvirt\_ceph\_secret

    Set the libvirt `secret` file and
    couple the `uuid` to the Ceph key from the `keyring`.

- \_do

    Convenience wrapper around CAF::Process

    Options

    - user: option passed to `CAF::Process`
    - sensitive: option passed to `CAF::Process`
    - test: the command is a test, no error will be reported on failure

- pre\_populate\_service\_database

    Run before the default service database is poulated
    (it is not run when database was already present).

    Must return 1 on success;

- populate\_service\_database

    Run the database sync command (incl bootstrap when empty)
    if db version cannot be found.

    Must return 1 on success.

- post\_populate\_service\_database

    Run after the service database is poulated
    (it is not run when database was already present).

    Must return 1 on success;

- restart\_daemons

    Restarts system service(s) after any configuration
    change for OpenStack `service` service.

- pre\_restart

    Run before possible restart of services
    Must return 1 on success

- run

    Do things (in following order):

    - write\_config\_file
    - populate\_service\_database (or return)
    - pre\_restart (or return)
    - restart\_daemons (if config file changed)
