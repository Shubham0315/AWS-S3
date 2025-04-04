What are S3 storage classes?
-
- AWS Offers different storage classes designed for various use cases based on access frequency, cost and durability.

- S3 Standard
  - Used for frequently accessed data
  - 99.99% durability and availability
  - Highest cost
  - Used for websites, apps, logs, hot data
 
- S3 Intelligent Tiering
  - Used for unknown or changing access patterns
  - 99.99% durability and availability
  - Cost lower than standard
  - Used in data lakes, analytics workloads
 
- S3 Standard IA (Infrequent Access)
  - Used for infrequently accessed data but needs quick retrieval
  - 99.99% durability and availability
  - Cost 40% lower than standard
  - Used for backups, DR, long term logs
 
- S3 One Zone IA
  - Infrequently accessed data that does not need multi AZ redundancy
  - 99.99% durability and 99.5% availability
  - Cost 20% lower than standard IA
 
- S3 Glacier
  - Used for long term archival storage
  - 99.99% durability and availability
  - Cost very low
  - Used for cold storage
 
- S3 Glacier Deep Archive
  - Used for data that is rarely accessed
  - 99.99% durability and availability
  - Lowest cost among S3 classes
  - Used for regulatory backups, scientific data
 
--------------------------------------------------------------------------------------

How is data organized in S3?
-
-
