# Infrastructure services

The network used supporting services that are common in enterprise operations:

- **DHCP / relay:** endpoint addressing across routed VLANs
- **DNS:** hostname resolution for managed infrastructure
- **NTP:** consistent timestamps for logs and troubleshooting
- **SSH:** remote device administration
- **TFTP:** centralized configuration backup

Raw backups are not appropriate for a public repository because they can expose usernames, hashes, keys, internal addresses, and other sensitive metadata.
