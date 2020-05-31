# Network Configuration Backup

**THIS IS A WORK IN PROGRESS**

As a network engineer I need to backup my network configuration files into a
version control system, and I would like a tool to automate this process.
    
    (*) I will have multi-vendor environment, and I will need to handle all
    different types of device SSH connections.  Some of the devices will
    require me to disable paging before I execute the command to get the
    running configuraiton.
    
    (*) I need to provide multiple SSH credendials so that the tool will try
    each credential provided in-order until either a login is successful, or
    all credentials are exhaused.  I need this feature because sometimes not
    all devices are configured with the same credentials, or may not be able to
    access the configured AAA server.
    
    (*) I might also want to obtain the device configuraitons from other NMS
    systems.  These NMS systems would be snapshotting the configuration on a
    nightly (or periodic) basis.  I could use the NMS API to retrieve the
    device configuration rather than SSH'ing to the device and have to deal
    with running commands via CLI.

    (*) I will have a large number of devices (>1000) so I want this tool to take
    advantage of any and all techniques that reduce the total amount of time.

    (*) I want this tool to use a minimum number of 3rd-party packages to
    minimize the risk of dependency sprawl.  For example, I do not want to
    include vendor specific libraries that can do everything under the kitchen
    sink just so I can do a config backup.
        
    (*) I want this tool to be easily extensible so that when I have other
    network devices added to my environment I can easily update this tool.  Ideally
    I do not want to write any new code, but rather use some form of configuraiton-file
    to achieve these extensions.
    
    