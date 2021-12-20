# optimizer-proxmox :: OverloadSolutions.net Proxmox (pve)

Scripts for working with and optimizing proxmox

## Maintained and provided by <https://overloadsolutions.net/>

## Optimization / Post Install Script (optimizer.sh aka postinstall.sh) *run once*
Turns a fresh proxmox install into an optimised proxmox host

'reboot-quick' command which uses kexec to boot the latest kernel, its a fast method of rebooting, without needing to do a hardware reboot

* Disable the enterprise repo, enable the public repo, Add non-free sources
* Fixes known bugs (public key missing, max user watches, etc)
* Update the system
* Detect AMD EPYC CPU and Apply Fixes
* Force APT to use IPv4
* Update proxmox and install various system utils
* Customise bashrc
* add the latest ceph provided by proxmox
* Disable portmapper / rpcbind (security)
* Ensure Entropy Pools are Populated, prevents slowdowns whilst waiting for entropy
* Protect the web interface with fail2ban
* Detect if is running in a virtual machine and install the relavant guest agent
* Install ifupdown2 for a virtual internal network allows rebootless networking changes (not compatible with openvswitch-switch)
* Limit the size and optimise journald
* Install kernel source headers
* Install kexec, allows for quick reboots into the latest updated kernel set as primary in the boot-loader.
* Ensure ksmtuned (ksm-control-daemon) is enabled and optimise according to ram size
* Set language, if chnaged will disable XS_NOAPTLANG
* Increase max user watches, FD limit, FD ulimit, max key limit, ulimits
* Optimise logrotate
* Lynis security scan tool by Cisofy
* Increase Max FS open files
* Optimise Memory
* Pretty MOTD BANNER
* Enable Network optimising
* Save bandwidth and skip downloading additional languages, requires XS_LANG="en_US.UTF-8"
* Disable enterprise proxmox repo
* Remove subscription banner
* Install openvswitch for a virtual internal network
* Detect if this is an OVH server and install OVH Real Time Monitoring
* Set pigz to replace gzip, 2x faster gzip compression
* Bugfix: high swap usage with low memory usage
* Enable TCP BBR congestion control
* Enable TCP fastopen
* Enable testing proxmox repo
* Automatically Synchronize the time
* Set Timezone, empty = set automatically by IP
* Install common system utilities
* Increase vzdump backup speed
* Optimise ZFS arc size accoring to memory size
* Install zfs-auto-snapshot

