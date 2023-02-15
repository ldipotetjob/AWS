
## Different ways to create credential provider in AWS


### Getting credentials from Environment Vars

#### Creating ENVIRONMENT VARIABLES 

```shell
export AWS_ACCESS_KEY=<paste your access key>
export AWS_SECRET_KEY=<paste your secret key>
```

#### Creating IAM CLIENT from ENV VARs

```python
import os

iam = boto3.client('iam',
                   aws_access_key_id=os.environ.get('AWS_ACCESS_KEY'),
                   aws_secret_access_key = os.environ.get('AWS_SECRET_KEY'),
                   region_name="eu-west-1")
```

=============================================================================
### Getting credentials from AWS Config File

Your configs file must reside in your local machine:</br>

1. ~/.aws/config 
2. ~/.aws/credentials


1. :
```
# file:
# ~/.aws/config

[default]
aws_access_key_id=<your_access_key_id>;
aws_secret_access_key=<your_secret_access_key>;
```

2. : 
```
# file:
# ~/.aws/credentials

[default]
aws_access_key_id=<your_access_key_id>;
aws_secret_access_key=<your_secret_access_key>;
```
