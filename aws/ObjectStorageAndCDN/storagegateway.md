# Storage gateway

- connects an on-premises software appliance with cloud-based storage to provide seamless and secure integration
- Storage Gateways software appliance is available for download as a virtual machine image
- supports VMware ESXi or Hyper-V
  - File Gateway (NFS) - S3
  - Volumes Gateway (iSCSI) : EBS snapshots , snapshots are incremental backups (only changed blocks)
    - Stored Volumes (1 to 16 TiB)- asynchronously backing up data to AWS, (mounted iSCSI virtual volumes -> EBS snapshots) - 100% copy of date on site
    - Cached Volumes (1 to 32 TiB)
  - Tape Gateway (VTL) : netbackup , virtual tapes

## Summary

- File Gateway - For flat files, sotred directly on S3.
- Volume Gateway
  - Stored Volumes - Entire Dataset is stored on site and is asynchronously backed up to S3.
  - Cached Volumes - Entire Dataset is stored on S3 and the most frequently accessed data is cached on site.
- Gateway Virtual Tape Library (VTL)
  - Used for backup and uses popular backup applications like NetBackup, Backup Exec, Veam etc
