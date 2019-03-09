# aws-cloudformation

## Overview
This repository will review a number of different approaches and architectures.

## Status
In development - NOTHING in here is production worthy.

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
