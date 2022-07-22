## Grant to s3 ##

### Grant a user Amazon S3 console access to only a certain bucket or folder ###

- List/Add/Get Bucket Objects 
```json
{
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket"
         ],
         "Resource":"arn:aws:s3:::DOC-EXAMPLE-BUCKET"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:PutObject",
            "s3:GetObject"
         ],
         "Resource":"arn:aws:s3:::DOC-EXAMPLE-BUCKET/*"
      }
   ]
}
```
</br>
</br>

- List/Add/Get Bucket Objects on specific folder
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowUsersToAccessFolder2Only",
            "Effect": "Allow",
            "Action": [
                "s3:GetObject*",
                "s3:PutObject*"
            ],
            "Resource": [
                "arn:aws:s3:::DOC-EXAMPLE-BUCKET/folder1/folder2/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket*"
            ],
            "Resource": [
                "arn:aws:s3:::DOC-EXAMPLE-BUCKET"
            ],
            "Condition": {
                "StringLike": {
                    "s3:prefix": [
                        "folder1/folder2/*"
                    ]
                }
            }
        }
    ]
}
```
</br>
</br>

- Do whatever you want in an specific  folder 
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::DOC-EXAMPLE-BUCKET",
                "arn:aws:s3:::DOC-EXAMPLE-BUCKET/*"
            ]
        }
    ]
}
```

</br>
</br>
ref:https://aws.amazon.com/premiumsupport/knowledge-center/s3-console-access-certain-bucket/

