## EC2 options
- On Demand
- Reserved - steady state or predictable usage
- Spot :
  - if your applications have flexible start and end times
  - only feasible at very low compute prices
  - urgent computing needs for large amounts of additional capacity
- Dedicated Hosts :
  - Physical EC2 server dedicated for your use. reduce costs by allowing you to use your existing server-bound software licenses.
  - regulatory requirements that not support multi-tenant virtualisation
  - licensing which does not support multi-tenancy or cloud deployments
  - ** can be purchased on-demand or Reserved

- DIRTMCGFPX
  - DR MC GIF(FPGA)T PX(Extreme memory)

## EBS

- EBS : storage volumes and attach them to EC2 instances. attached -> can create a file system
- placed in a specific AZ (automatically replicated protect single point of failure)

## EBS Volume Types
- General Purpose SSD (GP2)
  - price and performance
  - 3 IOPS per GB with up  to 10000 IOPS ( 3000 IOPS for extended period of time under 1 Gib)

- Provisioned IOPS SSD (IO1)
  - Nosql , SQL
  - need more 10000 IOPS
  - 20000 IOPS per volumes

- Throughput Optimized HDD (ST1)
  - Big data
  - Data warehouses
  - log processing
  - **Cannot be a boot volume**

- Cold HDD (SC1)
  - lowest Cost Storage for infrequently accessed
  - file server
  - cannot be a boot volumes

- Magnetic
  - Lowest cost (bootable)
  - ideal for workloads where data is accessed infrequently , and applications where the lowest storage cost is important

**By Default, After EC2 instance termination, EBS storage volume is deleted.**
**default AMI`s EBS root volume cannot be encrypted.**

**Security Group is stateful (means create inbound rule , then backed out without outbound rule)**

## RAID
- RAID 0 - Striped , No Redundancy, Good performance
- RAID 1 - Mirrored , Redundancy
- RAID 5 - Good for reads , bad for writes, AWS does not recommend ever putting RAID5s
- RAID 10 - Striped & Mirrored , Good Redundancy, Good performance

## RAID Snapshot problem
- snapshot exclude data held in the cache by applications and the os. this can be a problem because of interdependency
- application consistent Snapshot
  - Stop the application from writing to disck
  - Flush all caches to the disk.
  - Freeze the file system
  - Unmount the RAID Array
  - Shutting down the associated EC2 instance.

## EBS , instance storage
  - EBS from an Amazon EBS snapshot.
  - Instance Store from a template stored in Amazon S3.
