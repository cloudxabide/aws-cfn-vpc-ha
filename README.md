# aws-cloudformation

## Overview
This repository will review a number of different approaches and architectures.

## Status
In development - NOTHING in here is production worthy.

## Method(s).. maannn..
There is definitely conversation to be had about the merits of a single template vs nested templates.  Since I am still fairly new to all this, I'll leave that alone for now.  But, I *like* the concept of nested templates and separating your tech parameters by "concern" (compute vs security vs networking) which *should* allow for reusable artifacts.  
### Naming Standards
For now, I am using the following:
aws-\<project\>-\<numeric value\>-\<concern\>.yaml  
aws-hexgl-01-vpc.yaml  
aws-hexgl-02-securitygroups.yaml  
aws-hexgl-master.yaml  

The "master" template is the primary one to be called and will call the others (conditionally).  The numeric values are just asthetics, the value has no impact on what *actual* order the utilities will use them (you will manage the order in the "master" file).

### "Commands" file (cmds.txt)
I keep track of the commands frequently executued in the context of what I am doing.

### Parameter Files (params-*)
While this example is optimally created to be used with the CloudFormation webUI, for obvious reasons I would like to be able to submit (and resubmit) the job from the CLI with minimal user inputs.  One interesting thing to note: parameter files are *only* JSON at this time (early-2019).  Not sure that will change (not sure I care).  
params-us-east-1.json  
params-us-west-2.json  

## Projects
### HexGL App with CloudFormation
Deploy HexGL using CloudFormation and nested templates.  
[New VPC, Multi-AZ, EC2 instances running HTML5/javascript/webGL app](https://github.com/cloudxabide/aws-cloudformation-hexgl)  

## References
[Wordpress multi-AZ reference architecture](https://github.com/aws-samples/aws-refarch-wordpress)  
[Tips and Tricks](./tips-n-tricks.md)

