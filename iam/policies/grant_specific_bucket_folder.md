```json
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "AllowGroupToSeeBucketListInTheConsole",
			"Action": [
				"s3:ListAllMyBuckets",
				"s3:GetBucketLocation"
			],
			"Effect": "Allow",
			"Resource": "*"
		},
		{
			"Effect": "Allow",
			"Action": [
				"s3:ListBucket",
				"s3:GetObject",
				"s3:PutObject",
				"s3:DeleteObject"
			],
			"Resource": [
				"arn:aws:s3:::genhub-test-lambda"
			],
			"Condition": {
				"StringLike": {
					"s3:prefix": [
						"ldipotet@yello.com-20-par-1682509566501/*"
					]
				}
			}
		},
		{
			"Effect": "Allow",
			"Action": [
				"s3:GetObject",
				"s3:GetObject",
				"s3:PutObject",
				"s3:DeleteObject"
			],
			"Resource": [
				"arn:aws:s3:::genhub-test-lambda/ldipotet@yello.com-20-par-1682509566501/*"
			]
		},
		{
			"Effect": "Deny",
			"Action": [
				"s3:ListBucket",
				"s3:GetObject"
			],
			"Resource": [
				"arn:aws:s3:::genhub-test-lambda",
				"arn:aws:s3:::genhub-test-lambda/*"
			],
			"Condition": {
				"StringNotLike": {
					"s3:prefix": [
						"ldipotet@yello.com-20-par-1682509566501/*"
					]
				}
			}
		}
	]
}
```
