
### Pricing model for compute workload

What pricing model if best suited for your compute workload, so in these grah that reflect 
% iutilization yiu can have a look.
i.e if an ec2 instance is consistent on its use over time then reserved instances 
(impact-ec2instances-pricing-model)


### Cost-effective-high-cpu solution

Select a proper scaling strategy, check this scenario 
db experiencing performance issues because high cpu utilization, so options to solve this:
1- Increase RDS DB instance => increase the cost
2- Add read replica or something to cash data => best solution (scaling-strategy-issue-highcpu-utilization-solution2)

scaling-strategy-issue-highcpu-utilization-_

### Reducing cost on S3

One Way to optimize cost when using S3 is to reduce the amount of api calls:
Using content delivery services like for example CloudFront(cost-effective-solution-s3). In this solution you only call S3 when what you looking for is not found in the Cache

Cashing solution on S3 can reduce the transfer out from S3

AWS VPC connectivity options:
https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/introduction.html



