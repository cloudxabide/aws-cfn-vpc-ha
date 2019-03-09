# aws-cloudformation

## Overview
This repository will review a number of different approaches and architectures.

## Status
In development - NOTHING in here is production worthy.

## Method(s).. maannn..
There is definitely conversation to be had about the merits of a single template vs nested templates.  Since I am still fairly new to all this, I'll leave that alone for now.  But, I *like* the concept of nested templates and separating your tech parameters by "concern" (compute vs security vs networking) which *should* allow for reusable artifacts.  
### Naming Standards
For now, I am using the following:
aws-<project>-<numeric value>-<concern>.yaml  
aws-hexgl-01-vpc.yaml  
aws-hexgl-02-securitygroups.yaml  
aws-hexgl-master.yaml  

The "master" template is the primary one to be called and will call the others (conditionally).  The numeric values are just asthetics, the value has no impact on what *actual* order the utilities will use them (you will manage the order in the "master" file).

### "Commands" file (cmds.txt)
I keep track of the commands frequently executued in the context of what I am doing.

### Parameter Files (params-*)
While this example is optimally created to be used with the CloudFormation webUI, for obvious reasons I would like to be able to submit (and resubmit) the job from the CLI with minimal user inputs.  One interesting thing to note: parameter files are *only* JSON at this time (early-2019).  Not sure that will change (not sure I care).

## Projects
[99-newvpc-multiAZ](99-newvpc-multiAZ) -- This is my first successful deployment of a nested-stack deployment using separate templates for each individual "concern":  
aws-hexgl-master-newvpc.yaml  
aws-hexgl-01-newvpc.yaml  
aws-hexgl-02-securitygroups.yaml  
aws-hexgl-03-bastion.yaml  
aws-hexgl-03-publicalb.yaml  
aws-hexgl-04-web.yaml  

[98-newvpc-multiAZ-wSSL](98-newvpc-multiAZ-wSSL) -- Adding route53 to my nested stack deployment.  
[98-newvpc-multiAZ-wSSL/aws-hexgl-01-newvpc.yaml](98-newvpc-multiAZ-wSSL/aws-hexgl-01-newvpc.yaml)  
[98-newvpc-multiAZ-wSSL/aws-hexgl-02-securitygroups.yaml](98-newvpc-multiAZ-wSSL/aws-hexgl-02-securitygroups.yaml)  
[98-newvpc-multiAZ-wSSL/aws-hexgl-03-bastion.yaml](98-newvpc-multiAZ-wSSL/aws-hexgl-03-bastion.yaml)  
[98-newvpc-multiAZ-wSSL/aws-hexgl-03-publicalb.yaml](98-newvpc-multiAZ-wSSL/aws-hexgl-03-publicalb.yaml)    
[98-newvpc-multiAZ-wSSL/aws-hexgl-04-web.yaml](98-newvpc-multiAZ-wSSL/aws-hexgl-04-web.yaml)  
[98-newvpc-multiAZ-wSSL/aws-hexgl-05-route53.yaml](98-newvpc-multiAZ-wSSL/aws-hexgl-05-route53.yaml)  
[98-newvpc-multiAZ-wSSL/aws-hexgl-master-newvpc.yaml](98-newvpc-multiAZ-wSSL/aws-hexgl-master-newvpc.yaml)  


## References
[Wordpress multi-AZ reference architecture](https://github.com/aws-samples/aws-hexgl)  
[Tips and Tricks](./tips-n-tricks.md)

## CFN Launch Links

### [98-newvpc-multiAZ-wSSL](98-newvpc-multiAZ-wSSL) example

| AWS Region | Region Name | Launch Button 
| --- | --- | ---
| us-east-1 | US East (N. Virginia) |  [![cloudformation-launch-stack](images/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=WordPress&templateURL=https://s3.amazonaws.com/cloudxabide/aws-cloudformation/98-newvpc-multiAZ-wSSL/aws-hexgl-master-newvpc.yaml) |
| us-east-2 | US East (Ohio) | 
| us-west-1 | US West (N. California) | 
| us-west-2 | US West (Oregon) | 

If you prefer the CLI
```
REGION="us-east-1"
STACK_NAME="HEXGLE1"
aws cloudformation create-stack --stack-name "${STACK_NAME}" --template-url https://s3.amazonaws.com/cloudxabide/aws-cloudformation/98-newvpc-multiAZ-wSSL/aws-hexgl-master-newvpc.yaml --parameters https://s3.amazonaws.com/cloudxabide/aws-cloudformation/98-newvpc-multiAZ-wSSL/params-${REGION}.json --region ${REGION} --capabilities CAPABILITY_IAM ${OPTIONS}
```
