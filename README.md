# keyforcloudtrail
demokeyname

{
    "eventVersion": "1.08",
    "userIdentity": {
        "type": "Root",
        "principalId": "",
        "arn": "arn:aws:iam:::root",
        "accountId": "",
        "accessKeyId": "",
        "sessionContext": {
            "sessionIssuer": {},
            "webIdFederationData": {},
            "attributes": {
                "creationDate": "2024-02-26T05:24:16Z",
                "mfaAuthenticated": "false"
            }
        }
    },
    "eventTime": "2024-02-26T05:32:56Z",
    "eventSource": "kms.amazonaws.com",
    "eventName": "CreateKey",
    "awsRegion": "us-east-1",
    "sourceIPAddress": "110.225.137.11",
    "userAgent": "AWS Internal",
    "requestParameters": {
        "customerMasterKeySpec": "SYMMETRIC_DEFAULT",
        "bypassPolicyLockoutSafetyCheck": false,
        "policy": "{\n  \"Version\": \"2012-10-17\",\n  \"Id\": \"Key policy created by CloudTrail\",\n  \"Statement\": [\n    {\n      \"Sid\": \"Enable IAM User Permissions\",\n      \"Effect\": \"Allow\",\n      \"Principal\": {\n        \"AWS\": [\"arn:aws:iam::767398026910:root\", \"767398026910\"]\n      },\n      \"Action\": \"kms:*\",\n      \"Resource\": \"*\"\n    },\n    {\n      \"Sid\": \"Allow CloudTrail to encrypt logs\",\n      \"Effect\": \"Allow\",\n      \"Principal\": {\"Service\":\"cloudtrail.amazonaws.com\"},\n      \"Action\": \"kms:GenerateDataKey*\",\n      \"Resource\": \"*\",\n      \"Condition\": {\n        \"StringLike\": {\n          \"kms:EncryptionContext:aws:cloudtrail:arn\": [\n            \"arn:aws:cloudtrail:*:767398026910:trail/*\"\n          ]\n        },\n        \"StringEquals\": {\n          \"aws:SourceArn\": \"arn:aws:cloudtrail:us-east-1:767398026910:trail/demo-test\"\n        }\n      }\n    },\n    {\n      \"Sid\": \"Allow CloudTrail to describe key\",\n      \"Effect\": \"Allow\",\n      \"Principal\": {\"Service\":\"cloudtrail.amazonaws.com\"},\n      \"Action\": \"kms:DescribeKey\",\n      \"Resource\": \"*\"\n    },\n    {\n      \"Sid\": \"Allow principals in the account to decrypt log files\",\n      \"Effect\": \"Allow\",\n      \"Principal\": {\n        \"AWS\": \"*\"\n      },\n      \"Action\": [\n        \"kms:Decrypt\",\n        \"kms:ReEncryptFrom\"\n      ],\n      \"Resource\": \"*\",\n      \"Condition\": {\n        \"StringEquals\": {\n          \"kms:CallerAccount\": \"767398026910\"\n        },\n        \"StringLike\": {\n          \"kms:EncryptionContext:aws:cloudtrail:arn\": [\n            \"arn:aws:cloudtrail:*:767398026910:trail/*\"\n          ]\n        }\n      }\n    },\n    {\n      \"Sid\": \"Allow alias creation during setup\",\n      \"Effect\": \"Allow\",\n      \"Principal\": {\n        \"AWS\": \"*\"\n      },\n      \"Action\": [\n        \"kms:CreateAlias\"\n      ],\n      \"Resource\": \"*\",\n      \"Condition\": {\n        \"StringEquals\": {\n          \"kms:CallerAccount\": \"767398026910\",\n          \"kms:ViaService\": \"ec2.us-east-1.amazonaws.com\"\n        }\n      }\n    },\n    {\n      \"Sid\": \"Enable cross account log decryption\",\n      \"Effect\": \"Allow\",\n      \"Principal\": {\n        \"AWS\": \"*\"\n      },\n      \"Action\": [\n        \"kms:Decrypt\",\n        \"kms:ReEncryptFrom\"\n      ],\n      \"Resource\": \"*\",\n      \"Condition\": {\n        \"StringEquals\": {\n          \"kms:CallerAccount\": \"767398026910\"\n        },\n        \"StringLike\": {\n          \"kms:EncryptionContext:aws:cloudtrail:arn\": [\n            \"arn:aws:cloudtrail:*:767398026910:trail/*\"\n          ]\n        }\n      }\n    }\n  ]\n}\n",
        "keyUsage": "ENCRYPT_DECRYPT",
        "keySpec": "SYMMETRIC_DEFAULT",
        "origin": "AWS_KMS",
        "description": "The key created by CloudTrail to encrypt log files. Created Mon Feb 26 05:32:56 UTC 2024"
    },
    "responseElements": {
        "keyMetadata": {
            "aWSAccountId": "767398026910",
            "keyId": "1a86d97a-4d59-42cd-a589-c7ca42ad8aeb",
            "arn": "arn:aws:kms:us-east-1:767398026910:key/1a86d97a-4d59-42cd-a589-c7ca42ad8aeb",
            "creationDate": "Feb 26, 2024, 5:32:56 AM",
            "enabled": true,
            "description": "The key created by CloudTrail to encrypt log files. Created Mon Feb 26 05:32:56 UTC 2024",
            "keyUsage": "ENCRYPT_DECRYPT",
            "keyState": "Enabled",
            "origin": "AWS_KMS",
            "keyManager": "CUSTOMER",
            "customerMasterKeySpec": "SYMMETRIC_DEFAULT",
            "keySpec": "SYMMETRIC_DEFAULT",
            "encryptionAlgorithms": [
                "SYMMETRIC_DEFAULT"
            ],
            "multiRegion": false
        }
    },
    "requestID": "651028b2-1e89-4c25-b4fe-d6b4966c3120",
    "eventID": "0dd2995c-de8d-4235-ad0c-1621a4eb4a6e",
    "readOnly": false,
    "resources": [
        {
            "accountId": "767398026910",
            "type": "AWS::KMS::Key",
            "ARN": "arn:aws:kms:us-east-1:767398026910:key/1a86d97a-4d59-42cd-a589-c7ca42ad8aeb"
        }
    ],
    "eventType": "AwsApiCall",
    "managementEvent": true,
    "recipientAccountId": "767398026910",
    "eventCategory": "Management",
    "sessionCredentialFromConsole": "true"
}
