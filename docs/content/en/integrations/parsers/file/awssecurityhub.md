---
title: "AWS Security Hub"
toc_hide: true
---
### File Types
DefectDojo parser accepts a .json file. 

JSON reports can be created from the [AWS Security Hub CLI](https://docs.aws.amazon.com/cli/latest/reference/securityhub/get-findings.html) using the following command: `aws securityhub get-findings`.

### Acceptable JSON Format
Parser expects a .json file, with an array of Findings contained within a single JSON object.  All properties are strings and are required by the parser.

~~~
{
    "findings": [
            {
                "SchemaVersion": "2018-10-08",
                "Id": "arn:aws:securityhub:us-east-1:012345678912:subscription/aws-foundational-security-best-practices/v/1.0.0/IAM.5/finding/de861909-2d26-4e45-bd86-19d2ab6ceef1",
                "ProductArn": "arn:aws:securityhub:us-east-1::product/aws/securityhub",
                "GeneratorId": "aws-foundational-security-best-practices/v/1.0.0/IAM.5",
                "AwsAccountId": "012345678912",
                "Types": [
                    "Software and Configuration Checks/Industry and Regulatory Standards/AWS-Foundational-Security-Best-Practices"
                ],
                "FirstObservedAt": "2020-06-08T14:33:07.560Z",
                "LastObservedAt": "2020-06-14T21:02:53.940Z",
                "CreatedAt": "2020-06-08T14:33:07.560Z",
                "UpdatedAt": "2020-06-14T21:02:53.454Z",
                "Severity": {
                    "Product": 0,
                    "Label": "INFORMATIONAL",
                    "Normalized": 0,
                    "Original": "INFORMATIONAL"
                },
                "Title": "IAM.5 MFA should be enabled for all IAM users that have console password",
                "Description": "This AWS control checks whether AWS Multi-Factor Authentication (MFA) is enabled for all AWS Identity and Access Management (IAM) users that use a console password.",
                "Remediation": {
                    "Recommendation": {
                        "Text": "For directions on how to fix this issue, please consult the AWS Security Hub Foundational Security Best Practices documentation.",
                        "Url": "https://docs.aws.amazon.com/console/securityhub/IAM.5/remediation"
                    }
                },
                "ProductFields": {
                    "StandardsArn": "arn:aws:securityhub:::standards/aws-foundational-security-best-practices/v/1.0.0",
                    "StandardsSubscriptionArn": "arn:aws:securityhub:us-east-1:012345678912:subscription/aws-foundational-security-best-practices/v/1.0.0",
                    "ControlId": "IAM.5",
                    "RecommendationUrl": "https://docs.aws.amazon.com/console/securityhub/IAM.5/remediation",
                    "RelatedAWSResources:0/name": "securityhub-mfa-enabled-for-iam-console-access-9ae73a2f",
                    "RelatedAWSResources:0/type": "AWS::Config::ConfigRule",
                    "StandardsControlArn": "arn:aws:securityhub:us-east-1:012345678912:control/aws-foundational-security-best-practices/v/1.0.0/IAM.5",
                    "aws/securityhub/SeverityLabel": "INFORMATIONAL",
                    "aws/securityhub/ProductName": "Security Hub",
                    "aws/securityhub/CompanyName": "AWS",
                    "aws/securityhub/annotation": "AWS Config evaluated your resources against the rule. The rule did not apply to the AWS resources in its scope, the specified resources were deleted, or the evaluation results were deleted.",
                    "aws/securityhub/FindingId": "arn:aws:securityhub:us-east-1::product/aws/securityhub/arn:aws:securityhub:us-east-1:012345678912:subscription/aws-foundational-security-best-practices/v/1.0.0/IAM.5/finding/de861909-2d26-4e45-bd86-19d2ab6ceef1"
                },
                "Resources": [
                    {
                        "Type": "AwsAccount",
                        "Id": "AWS::::Account:012345678912",
                        "Partition": "aws",
                        "Region": "us-east-1"
                    }
                ],
                "Compliance": {
                    "Status": "PASSED",
                    "StatusReasons": [
                        {
                            "ReasonCode": "CONFIG_EVALUATIONS_EMPTY",
                            "Description": "AWS Config evaluated your resources against the rule. The rule did not apply to the AWS resources in its scope, the specified resources were deleted, or the evaluation results were deleted."
                        }
                    ]
                },
                "WorkflowState": "NEW",
                "Workflow": {
                    "Status": "NEW"
                },
                "RecordState": "ACTIVE"
            },
        ...
    ]
}


~~~

### Sample Scan Data
Sample scan data for testing purposes can be found [here](https://github.com/DefectDojo/django-DefectDojo/tree/master/unittests/scans/awssecurityhub).