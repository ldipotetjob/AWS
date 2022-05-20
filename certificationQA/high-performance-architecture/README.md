## Things to take in count when designing high performance architecture 


What we are optmizing for ?
i.e: 
When optimizing for the least amount operational overhead?
When optimizing for the least amount of rework for a migration?
How can we deal with the communication between applications  in different regions or AZ . Depending on the service tha we're  using? 

Using storage desingned depending of a use case in mind. i.e:
Know what services are for BlockStorage and what for filestorage  
Know what services are for reading a what for writing data
How each storage is setup?

When each offload data request to caches to increase the performance:

*Read replicas for Amazon RDS
*DynamoDB acelerator for DynamoDB
*Amazon Elasic cache for Redis  
*Amazon Elasic cache for Memcache

When talking about read replicas:
Which database engine allow for read replicas across regions or AZ and which not

Use case for each networking solution(hint-highperforming-networking)(hint6-highperforming-conectivity)
General step for setting up and how mitigate  the issues?(uses cases multi-az, multi-region deployment)
How to  mitigate issues and how deal with disaster recovery.

