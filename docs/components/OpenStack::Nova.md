
####  Methods

- \_attrs

    Override `daemons` attribute

- pre\_populate\_service\_database

    Initializes API, cell and placement databases
    for `Nova` compute service.

- pre\_restart

    Run before services restart. Used for hypervisors post-configuration.

    Must return 1 on success;
