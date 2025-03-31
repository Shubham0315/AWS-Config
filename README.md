# AWS-Config

- AWS Config makes sure that our AWS account or resources aligns with rules and regulations of our organization

-------------------------------------------------------------------------------------------------------

Practical Demo
-
- Create 2 EC2 instances

![image](https://github.com/user-attachments/assets/e0d3416e-44de-4f0b-bae3-2ef78c4a315c)

- Suppose in our organization there is a rule that if EC2 is created, monitoring should be enabled. This can be for tracking the things happening on EC2 in case of any issues.
  - Inside instances - Monitoring - Manage Detailed Monitoring - Enabled
 
<img width="962" alt="image" src="https://github.com/user-attachments/assets/e2f0f0ca-94fd-4116-af20-47d85ef048d2" />

![image](https://github.com/user-attachments/assets/81af9126-aead-4b27-93ff-6a3826b74115)


  - If any of our EC2 is not adhering to this rule, it is out of compliance. 
  - So we've created 2 instances, one is adhering the rule while other isn't

- This rule can be applied for all AWS resources. Like S3 should have lifecycle management enabled or public access disabled.
- How we can ensure that our AWS account adheres to compliance rules of organizations? As DevOps engineer its our responsibility.
- For this DevOps engineer can use AWS config
  - Search Config :- Its for tracking resource inventory and changes. Using this we can check the compliance of all AWS resources
  - In Config we can create many rules
  - We can create rule and integrate with Lambda function.
  - Here we can setup rule like calling lambda function when any action happens regarding EC2 (Create,delete,modify).
  - Here AWS config invokes lambda function and it checks if EC2 has monitoring enabled or not. And fetching all info from EC2, we send it to AWS config
  - If we change the monitoring to enabled for other instance as well, it will trigger lambda, fetch all the EC2 info and provide it to config.
