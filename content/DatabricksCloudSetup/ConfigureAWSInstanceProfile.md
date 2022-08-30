+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Configure AWS Instance Profile"
date = 2019-09-09T17:42:10+01:00
weight = 20
+++

### 2. Setup IAM Role - Instance profile for Kinesis Stream and S3

#### Background

Below are the steps to  setup an Instance Profile ( IAM Role)  on your AWS Environment which will be used by your  Databricks Workspace environment .This instance profile setup is mandatory for the  communication between ,the  Kinesis Stream of your  AWS environment and  your Databricks workspace environment.

1. On the AWS account console go to IAM service, navigate to Roles and click ‘Create role’ button. Choose Trusted Entity Type -> AWS Service  and Use Case -> EC2 , Click Next

![Trusted Entity](/images/trusted-entity-type.png)

2. Choose the Permission Policy => `AmazonKinesisReadOnlyAccess`    and   `AmazonS3FullAccess`

![Instance Profile](/images/intance-profile-1.png)

3. Give Role Name as ```databricks-instance-profile-iam-role``` and click **"Create Role"**

4. Note/Copy down the role ARN and Instance Profile ARN of the IAM Role created above.

The role ARN will look like: ```arn:aws:iam::<Your AWS Account ID>:role/databricks-instance-profile-iam-role```

For Example: arn:aws:iam::117894312491:role/databricks-instance-profile-iam-role


The Instance Profile ARN will look like: ```arn:aws:iam::<Your AWS Account ID>:instance-profile/databricks-instance-profile-iam-role```

 For Example:   arn:aws:iam::117894312491:instance-profile/databricks-instance-profile-iam-role

These details can be found on the role page as shown here:

![ARN details](/images/arn-instance-profile.png)

5. In the AWS Console IAM Service, search for the Cross Account IAM Role which was created by the CloudFormation stack for Databricks Workspace creation.

It would look like: `db-e8b9a21f39fe8f132e24849656de948e-iam-role`

![Search details](/images/search-db-iam-role.png)

- Click on the role and open it
- In the ‘Permissions’ Tab, click the + symbol for the policy `databricks-cross-account-iam-role-policy`
- Edit/ the existing policy JSON of `databricks-cross-account-iam-role-policy`
- Add the following role JSON section to the Statement array as shown here (replace "Your AWS Account ID" with your AWS account ID):

```Json
{
    "Effect": "Allow",
    "Action": "iam:PassRole",
    "Resource": "arn:aws:iam::<Your AWS Account ID>:role/databricks-instance-profile-iam-role"
}
```

- Click on ‘Review Policy’ Button
- Click on ‘Save changes Button

The full role policy will look like this:

```Json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "ec2:AllocateAddress",
        "ec2:AssociateDhcpOptions",
        "ec2:AssociateIamInstanceProfile",
        "ec2:AssociateRouteTable",
        "ec2:AttachInternetGateway",
        "ec2:AttachVolume",
        "ec2:AuthorizeSecurityGroupEgress",
        "ec2:AuthorizeSecurityGroupIngress",
        "ec2:CancelSpotInstanceRequests",
        "ec2:CreateDhcpOptions",
        "ec2:CreateInternetGateway",
        "ec2:CreateKeyPair",
        "ec2:CreateNatGateway",
        "ec2:CreatePlacementGroup",
        "ec2:CreateRoute",
        "ec2:CreateRouteTable",
        "ec2:CreateSecurityGroup",
        "ec2:CreateSubnet",
        "ec2:CreateTags",
        "ec2:CreateVolume",
        "ec2:CreateVpc",
        "ec2:CreateVpcEndpoint",
        "ec2:DeleteDhcpOptions",
        "ec2:DeleteInternetGateway",
        "ec2:DeleteKeyPair",
        "ec2:DeleteNatGateway",
        "ec2:DeletePlacementGroup",
        "ec2:DeleteRoute",
        "ec2:DeleteRouteTable",
        "ec2:DeleteSecurityGroup",
        "ec2:DeleteSubnet",
        "ec2:DeleteTags",
        "ec2:DeleteVolume",
        "ec2:DeleteVpc",
        "ec2:DeleteVpcEndpoints",
        "ec2:DescribeAvailabilityZones",
        "ec2:DescribeIamInstanceProfileAssociations",
        "ec2:DescribeInstanceStatus",
        "ec2:DescribeInstances",
        "ec2:DescribeInternetGateways",
        "ec2:DescribeNatGateways",
        "ec2:DescribePlacementGroups",
        "ec2:DescribePrefixLists",
        "ec2:DescribeReservedInstancesOfferings",
        "ec2:DescribeRouteTables",
        "ec2:DescribeSecurityGroups",
        "ec2:DescribeSpotInstanceRequests",
        "ec2:DescribeSpotPriceHistory",
        "ec2:DescribeSubnets",
        "ec2:DescribeVolumes",
        "ec2:DescribeVpcs",
        "ec2:DetachInternetGateway",
        "ec2:DisassociateIamInstanceProfile",
        "ec2:DisassociateRouteTable",
        "ec2:ModifyVpcAttribute",
        "ec2:ReleaseAddress",
        "ec2:ReplaceIamInstanceProfileAssociation",
        "ec2:ReplaceRoute",
        "ec2:RequestSpotInstances",
        "ec2:RevokeSecurityGroupEgress",
        "ec2:RevokeSecurityGroupIngress",
        "ec2:RunInstances",
        "ec2:TerminateInstances"
      ],
      "Resource": [
        "*"
      ],
      "Effect": "Allow",
      "Sid": "Stmt1403287045000"
    },
    {
      "Condition": {
        "StringLike": {
          "iam:AWSServiceName": "spot.amazonaws.com"
        }
      },
      "Action": [
        "iam:CreateServiceLinkedRole",
        "iam:PutRolePolicy"
      ],
      "Resource": [
        "arn:aws:iam::*:role/aws-service-role/spot.amazonaws.com/AWSServiceRoleForEC2Spot"
      ],
      "Effect": "Allow"
    },
    {
      "Effect": "Allow",
      "Action": "iam:PassRole",
      "Resource": "arn:aws:iam::<Your AWS Account ID>:role/databricks-instance-profile-iam-role"
    }
  ]
}
```

This cross account policy will now allow workspace instances to access Amazon Kinesis and Amazon S3 for streaming analytics and ML.

Now let's configure your Databricks workspace to use the instance profile above.

