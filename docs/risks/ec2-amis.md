# EC2 AMIs (Machine Images)

## Steps to Reproduce

## Example

## Exploitation

## Remediation

> ‼️ **Note**: At the time of this writing, AWS Access Analyzer does **NOT** support auditing of this resource type to prevent resource exposure. **We kindly suggest to the AWS Team that they support all resources that can be attacked using this tool**. 😊

* **Trusted Accounts Only**: Ensure that EC2 AMIs are only shared with trusted accounts, and that the trusted accounts truly need access to the EC2 AMIs.
* **Ensure access is necessary**: For any trusted accounts that do have access, ensure that the access is absolutely necessary.
* **Restrict access to IAM permissions that could lead to exposure of your AMIs**: Tightly control access to the following IAM actions:
  - [ec2:ModifyImageAttribute](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_ModifyImageAttribute.html): _Grants permission to modify an attribute of an Amazon Machine Image (AMI)_
  - [ec2:DescribeImageAttribute](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeImageAttribute.html): _Grants permission to describe an attribute of an Amazon Machine Image (AMI). This includes information on which accounts have access to the AMI_
  - [ec2:DescribeImages](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeImages.html): _Grants permission to describe one or more images (AMIs, AKIs, and ARIs)_

Also, consider using [Cloudsplaining](https://github.com/salesforce/cloudsplaining/#cloudsplaining) to identify violations of least privilege in IAM policies. This can help limit the IAM principals that have access to the actions that could perform Resource Exposure activities. See the example report [here](https://opensource.salesforce.com/cloudsplaining/)

## References

- [aws ec2 modify-image-attribute](https://docs.aws.amazon.com/cli/latest/reference/ec2/modify-image-attribute.html)