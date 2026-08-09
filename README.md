# soc-lab

Home security lab: endpoint telemetry, log collection, and detection.
Notes and writeups live in `/notes`.

## Hardware
- 2x Dell OptiPlex USFF — i3-6100T, 8GB RAM
- 1x Dell OptiPlex desktop — i3-4150, 8GB RAM
- Additional spare units, currently unused

## Current state
- One USFF running Proxmox
- various container services running:
    - pihole
    - portainer
    - Nginx Proxy manager
- Next: Windows VM + Sysmon, then Wazuh on a second box
