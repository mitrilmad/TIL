## Creating AMI , Encrypted Root volumes
- when creating root volume snapshot, instance should shut down for consistency.
- snapshot can be copied for other region.
- procedure :
  - make snapshot
  - copy snapshot : check **Encryption** option.
- can share only unencrypted snapshot. (encryption key is tied for you)
