# List of considerations before installing PBS

The following considerations were taken from the PBS Professional Big Book 19.2.3:

1. Run the same version of PBS on all devices.
2. Disk space recommended for the installation is to have at least 350 MB. It does not include LOG files.
3. Firewalls:
   1. PBS needs to use any port for outgoing connections.
   2. For incoming connections, PBS server and MoM daemons use ports 15001 through 15007 by default. PBS communication daemon listens on port 17001.
4. Network and name resolution
   1. Your kernel must allow UDP and TCP connections. ARP and name solution server must be enabled as well.
   2. On the server/scheduler/communication host, the short name must resolve to the correct IP address.
   3. On the server/scheduler/communication host, the IP address must reverse resolve to the canonical name.
   4. Every MoM must resolve each MoM to the same IP address that the server recognizes for that MoM. So if the server recognizes MoM A at IP address w.x.y.z, all other MoMs must resolve MoM A to w.x.y.z.
5. NFS: Asynchronous writes to an NFS server can cause reliability problems. If using an NFS file system, mount the NFS file system synchronously (without caching.)
6. System Clocks in Sync: It is recommended that clocks on all participating systems be in sync.
7. User accounts:
   1. Users who will submit jobs must have accounts at the server and at each execution host.
