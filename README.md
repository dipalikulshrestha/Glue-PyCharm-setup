# Glue-PyCharm-setup
Glue-PyCharm-setup for interactive Glue sessions

## Overview
PyCharm is the favourite IDE for our Developers, Data analysts and Data scientists to write python scripts in order to analyze or transform the data.
Now, As part of Digital Transformation journey organizations now have increased footprints on AWS cloud. So, business data is currently available on both on-premise & cloud. While working on New business requirements, Data Scientist and Analyst need to analyse data or perform some transformations on both data sets available on on-prem and AWS. However, as such, there is no integration exists between Glue ETL and PyCharm for interactive development.
if our data teams can somehow connect with AWS GLue from local on-premise PyCharm that will be like a boon to our developers and will simplify their data analysis and processess and increase their productivity from day 1.
Interactive glue sessions allows programmers to build, test, run data preparation in analytics applications faster and more easily than ever before by providing open source jupyter kernel that can be integrated almost anywhere jupyter notebooks can. So this allows us to start apache spark sessions very quickly with 1 min billing minimum and excessive cost control features. interactive sessions are serverless so you dont have to worry about managiing th ecluster and focus on writing code to sort data challenges. 

## Technical Architecture
![image](https://user-images.githubusercontent.com/38211382/224697695-a09fd1dd-8c46-44ac-8cc6-6451d1312a3f.png)

## Technical implementation
Now for this set-up, we mainly need to set up 2 things
1. IAM permissions
2. Developement Environment

IAM
Client Principal Role - to allow access to AWS glue resources [ This is where you can segregate authentication for different teams by having one role per team, and can also apply Tag based access control for sessions]
Run time session roles : Needed to authour glue ETL job and to create interactive sessions 

### Pre-requisites
 AWS Account
 Python 3.7 or above
 Pycharm Professional edition ( to run jupyter notebooks in Pycharm)
 
 ## Setup Development Environment
 
 Create new Project in Pycharm
 Create new virtual env with base interpreter 3.10 
 Install libraries

```
pip3 install –upgrade jupyter boto3 aws-glue-sessions

```
Configure Jupyter Kernel
Find location of glue-sessions folder

```
pip3 show aws-glue-sessions

jupyter-kernelspec install glue_pyspark

jupyter-kernelspec install glue_spark
```

### Security Configurations

Set-up region
```
%region <region-code>
```

Set-up VPC
```
%connection <connection-name>
```

Set-up iam role
```
%iam_role <glue-interactive-role-name>
```

### Cost Configurations

Set-up timeout
```
%timeout <region-code>
```

Set-up no. of workers
```
%workers <connection-name>
```


