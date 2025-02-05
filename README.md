# Cost-Optimization
## Stale resources - EBS Snapshots
* Stale resources are something that are created and not used. 
* Cloud cost goes high with these resources. We can send notifications to certain persons or teams about the stale resources.

* I am using Lambda functions for EBS Snapshots
* I created a python script in Lambda function for EBS snapshots, using module in python called boto3 which can communicate with AWS resources. 
* we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

1. The Lambda function fetches all EBS snapshots owned by the same account ('self') 
2. Retrieves a list of active EC2 instances (running and stopped). 
3. For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. 
4. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs. 

## Permissions for Lambda function
* Give necessary permissions for Lambda role to describe/List snapshots, delete snapshots, 
* Also give permissions for EC2 instance to describe instances and volumes attached to it. 
* Default execution time for Lambda function is 3 sec.


