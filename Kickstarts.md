Kickstart files for CentOS 7
============================

Basic command line only CentOS 7
--------------------------------
A basic kickstart file for a commandline only CentOS x86_64:

* Password for the root account: centos
* Disk layout:
  * 1GB swap partition
  * The remainder is used for an ext4 root partition
* Packages: only the group 'core'
* No X configuration
* No graphical installation

The files:

* [centos7-basic-dhcp.cfg](centos7-basic-dhcp.cfg): with DHCP
* [centos7-basic-static_ipv4.cfg](centos7-basic-static_ipv4.cfg): with a static IPv4 ip address

Kickstart files for CentOS 6
============================

Raid setups using ext4
----------------------
* [centos6-raid0-ext4.cfg](centos6-raid0-ext4.cfg): RAID 0 or striping, using the disks sda and sdb
* [centos6-raid1-ext4.cfg](centos6-raid1-ext4.cfg): RAID 1 or mirrorring, using the disks sda and sdb
* [centos6-raid5-ext4.cfg](centos6-raid5-ext4.cfg): RAID 5, using the disks sda, sdb, sdc and sdd

Raid setups using ext3
----------------------
* [centos6-raid0.cfg](centos6-raid0.cfg): RAID 0 or striping, using the disks sda and sdb
* [centos6-raid1.cfg](centos6-raid1.cfg): RAID 1 or mirrorring, using the disks sda and sdb
* [centos6-raid5.cfg](centos6-raid5.cfg): RAID 5, using the disks sda, sdb, sdc and sdd

Kickstart files used at [NOC-PS](http://www.noc-ps.com)
-------------------------------------------------------
These kickstart files have the following in common:

* Network: static IP address
* Password for the root account: centostest
* Password for a user account 'charlie': centostest
* DNS is not available during installation
* A local caching nameserver is installed and used
* No X configuration
* No graphical installation

The files:

* [centos6-nocps-raid1.cfg](centos6-nocps-raid1.cfg): a RAID 1 or mirrorring setup using the disks sda and sdb for a 250MB ext2 /boot partition and an LVM containing a swap, /root and /tmp filesystems (both ext3)
* [centos6-nocps-standard.cfg](centos6-nocps-standard.cfg): a 250MB ext2 /boot partition and an LVM containing a swap, /root and /tmp filesystems (both ext4)

[OpenNebula](http://opennebula.org/)
------------------------------------
A basic CentOS 6 x86_64 installation for an OpenNebula VM:

* Network: DHCP
* Adds the (old?) OpenNebula repository at https://nazar.karan.org/results/opennebula/
* The opennebula-context package is installed for automatic configuration at bootup in an OpenNebula setup
* Serial console settings are removed from /etc/grub.conf
* The fixed MAC address is removed from the network setup to avoid the creation of a new network interface each time the MAC address changes

[CentOS-6-x86_64-OpenNebula.cfg](CentOS-6-x86_64-OpenNebula.cfg)

Basic desktop
-------------
An automatically generated kickstart file for desktop systems: [basic-desktop.cfg](basic-desktop.cfg)

Kickstart files for CentOS 5
============================
RAID setups
-----------
* [centos5-raid0.cfg](centos5-raid0.cfg): a RAID 0 configuration on the disks sda and sdb
* [centos5-raid1.cfg](centos5-raid1.cfg): a RAID 1 configuration on the disks sda and sdb
* [centos5-raid5.cfg](centos5-raid5.cfg): a RAID 5 configuration on the disks sda, sdb, sdc and sdd

[batata.cfg](batata.cfg)
------------------------
Kickstart file for a CentOS 5 Xen dom0 32bit with post scripts for:

* yum update
* kerberos authentication
* autofs
* nfs
* amanda
* logrotate
* sudo
* sshd
* an authorized ssh key for the root account
* grub: use the xen kernel
* hosts.allow and hosts.deny
* a bridge br0 containing eth0


To be investigated - TODO
-------------------------
* [centos-test.cfg](centos-test.cfg)
* [ks-centos5-64.cfg](ks-centos5-64.cfg)
* [ks-minimalC5-32.cfg](ks-minimalC5-32.cfg)
* [ks-minimalC5-64.cfg](ks-minimalC5-64.cfg)
* [workstation-ks.cfg](workstation-ks.cfg): USGCB standard desktop baseline
* [secure-kickstart.cfg](secure-kickstart.cfg): kickstart file with many of the [DISA STIG](http://en.wikipedia.org/wiki/Security_Technical_Implementation_Guide) changes applied via %post scripts.

Kickstart fiels for CentOS 4
============================

RAID setups
-----------
* [centos4-raid0.cfg](centos4-raid0.cfg): a RAID 0 (striping) configuration on the disks sda and sdb.
* [centos4-raid1.cfg](centos4-raid1.cfg): a RAID 1 (mirroring) configuration on the disks sda and sdb.
* [centos4-raid5.cfg](centos4-raid5.cfg): a RAID 5 configuration on the disks sda, sdb, sdc and sdd.

Unknown - TODO
==============
* [everything.cfg](everything.cfg)
* [ks-minimalC6.cfg](ks-minimalC6.cfg)
* [kvm-host.cfg](kvm-host.cfg)
* [lan-cluster-node.cfg](lan-cluster-node.cfg)
* [near-everything.cfg](near-everything.cfg)
