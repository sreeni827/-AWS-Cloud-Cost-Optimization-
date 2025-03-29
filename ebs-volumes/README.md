# AWS Lambda - Automatic Cleanup of Unused EBS Volumes

## **Overview**
This AWS Lambda function identifies and deletes **unattached EBS volumes** to optimize cloud storage costs.  
Unattached EBS volumes continue to incur charges, leading to unnecessary expenses. This function ensures cost efficiency by automatically removing unused volumes.  

## **How It Works**
1. The function lists all **EBS volumes** in the AWS account.  
2. It filters volumes that are in the `available` state (not attached to any EC2 instance).  
3. It deletes those unused volumes, ensuring no accidental cost leakage.  
4. The function is triggered via **AWS CloudWatch Events** to run at scheduled intervals.  

## **Setup Instructions**
1. **Create an AWS Lambda function**:
   - Runtime: **Python 3.x**
   - IAM Role: Attach **AmazonEC2FullAccess** or create a custom policy to allow volume deletion.  

2. **Attach a CloudWatch Event Trigger**:
   - Event Rule: **Schedule (e.g., run every 24 hours)**  
   - Target: **The created Lambda function**  

3. **Deploy the Python script (provided below) to your Lambda function.**  

## **Python Code**
Refer to the `lambda_function.py` file for the implementation.

## **Testing**
- Manually trigger the Lambda function from the AWS Console.  
- Check AWS **EC2 → Volumes** before and after execution to verify cleanup.  
- View logs in **AWS CloudWatch** to confirm volume deletions.  

## **Cost Savings**
By automating unused volume cleanup, organizations can **reduce AWS storage costs significantly**, especially in environments with frequent provisioning and decommissioning of EC2 instances.

---
