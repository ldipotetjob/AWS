## Connecting lambda function with postgres DB 

### Points to pay attention:

1. Python version
2. POSTGRES version
3. Environment (development/testing/production)

For environments like **development/testing** we have some guidance and solution for **psycopg-binary**:

1. Download psycopg2 dependencies based on your Python version. Pay attention to the **upload_lambda_directory** directory in the following code:  

```shell
## have been tested 3.8/3.9/3.10
## this sample is running with 3.11 
 
version=3.11 
docker run --name piplauncher --rm -ti \
--mount src="$(pwd)",target=/data,type=bind python:$version-slim \
pip install psycopg2-binary -t /data/upload_lambda_directory
```

2. Generated dependencies after install psycopg2-binary in your upload_lambda_directory 

* psycopg2
* psycopg2_binary-2.9.7.dist-info
* psycopg2_binary.libs

3. Add your lambda_function.py at your **upload_lambda_directory**. See below the the final directory structure:

```
├── ......
└── upload_lambda_directory
    ├── lambda_function.py
    ├── psycopg2
    ├── psycopg2_binary-2.9.7.dist-info
    └── psycopg2_binary.libs
 ```

4. The next step is to create the package.zip that compresses the dependencies + lambda_function.py (3folders + lambda_function.py)

```
├── ......
└── upload_lambda_directory
    ├── lambda_function.py
    ├── psycopg2
    ├── psycopg2_binary-2.9.7.dist-info
    ├── psycopg2_binary.libs
    └── package.zip
 ```

5. Update your lambda function uploading from zip **package.zip** from your **aws console** or by **aws cli**.

Dependencies **3.9/3.10/3.11**:

1. Lambda Python ver: 3.9
2. Lambda Python ver: 3.10
3. Lambda Python ver: 3.11





ref: [psycopg-vs-psycopg](https://www.psycopg.org/docs/install.html#psycopg-vs-psycopg-binary)

