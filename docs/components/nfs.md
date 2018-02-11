
### NAME

nfs: NCM component for `/etc/exports` and `/etc/fstab`

### DESCRIPTION

The _nfs_ component manages entries for `NFS` in the `/etc/exports`
and/or `NFS`/`NFSv4`/`Ceph`/`PanFS`/`bind` mount in the `/etc/fstab` files.

### Example

    prefix "/software/components/nfs";
    "exports" = append(dict(
        "path", "/shared/path/",
        "hosts", dict(
            "server*.example.org", "no_root_squash",
        ),
    ));

    "mounts" = append(dict(
        "device", "foreign.example.org:/shared/path/",
        "mountpoint", "/mnt/foreign",
        "fstype", "nfs",
        "options", "rw",
    ));

#### Functions

- mount\_action\_new\_old

    Compares two fstab hashref `new` and `old` for equality,
    and returns mount action to be taken.

    - If old does not exist, mount.
    - If equal, do nothing.
    - If the entries differ in the devices or mountpoint, do unmount/mount.
    - Otherwise, remount.

- fstab\_add\_defaults

    Given fstab hashref, add defaults for the undefined values
    Returns a copy of the original hashref

- parse\_fstab\_line

    Parses a line of `/etc/fstab` and converts it
    in a hashref.

    Returns undef when the line is comment/empty.

    Defaults are added using `fstab_add_defaults` function.

#### Methods

- exports

    Given the component configuration hashref `tree`,
    create the exports configuration file `/etc/exports`.
    A backup of the old file is created.

    The method also sets the `sync` option if nethier sync or async
    is specified.

    Returns if the configuration file changed (or not).

- fstab

    Given the component configuration hashref `tree`,
    create the fstab configuration file `/etc/fstab`.
    A backup of the old file is created.

    The fstab configuration file is read and processed. Any non-managed
    entries (and comments not related to the component) are left alone.

    Only managed entries are considered for removal or modifications;
    new ones are added from the configuration.

    The current managed entries are

    - devices with filesystems `nfs`, `nfs4`, `panfs` or [ceph](../components/ceph.md).
    - bind mounts (filesystem `none` and mount option `bind`)

    Method returns

    - if the configuration file changed (or not)
    - hashref with the old managed entries
    (key the device and value the fstab hashref
    from `parse_fstab_line` function)
    - arrayref with the order of the old managed devices \\%new, \\@new\_order;
    - hashref with the configured managed entries (with defaults
    and action to take added)
    - arrayref with the order of the configured devices

- do\_mount

    Do something mount(point) related (umount, mount, remount, ...)
    `cmd` is the arrayref, the mountpoint is appended from the [fstab](../components/fstab.md) hashref.

    Returns SUCCESS on success, undef on failure.

- process\_mounts

    Given the component configuration hashref `tree`,
    determine the new and old ncm-nfs managed entries via
    the [fstab](../components/fstab.md) method and do the appropriate unmounting/mounting.

    Returns

    - if the fstab configuration file changed (or not)
    (value from [fstab](../components/fstab.md) method)
    - if any mount action was taken
