# AWS Cloud Cost Optimization - Identifying Stale EBS Snapshots

## Overview
This project automates the deletion of stale Amazon EBS snapshots to optimize AWS storage costs. The solution uses an AWS Lambda function triggered by Amazon CloudWatch.

## How It Works
- The Lambda function fetches all EBS snapshots owned by the AWS account.
- It retrieves active EC2 instances and their associated volumes.
- It identifies and deletes snapshots that:
  - Are not attached to any volume.
  - Are linked to a deleted volume.
  - Are associated with a volume not attached to a running instance.

## AWS Services Used
- **AWS Lambda** - Runs the automation script.
- **Amazon CloudWatch** - Triggers the Lambda function on a schedule.
- **Amazon EC2** - Provides snapshot and instance data.

## Setup Instructions
1. Create an AWS Lambda function using Python 3.x.
2. Assign an IAM role with permissions for EC2 and snapshots.
3. Deploy the Python script:
4. Set up an Amazon CloudWatch rule to trigger the function.

## Benefits
- Automates cost savings by removing unused snapshots.
- Improves AWS resource efficiency.
- Reduces manual maintenance efforts.

This simple automation ensures a clean and cost-effective cloud environment.


