# aws-cloudformation

## Overview
This repository will review a number of different approaches and architectures.

## Status
In development - NOTHING in here is production worthy.

## Projects
[99-newvpc-multiAZ](99-newvpc-multiAZ) -- This is my first successful deployment of a nested-stack deployment using separate templates for each individual "concern":  
aws-refarch-wordpress-master-newvpc.yaml  
aws-refarch-wordpress-01-newvpc.yaml  
aws-refarch-wordpress-02-securitygroups.yaml  
aws-refarch-wordpress-03-bastion.yaml  
aws-refarch-wordpress-03-publicalb.yaml  
aws-refarch-wordpress-04-web.yaml  

## References

[Wordpress multi-AZ reference architecture](https://github.com/aws-samples/aws-refarch-wordpress)  
[Tips and Tricks](./tips-n-tricks.md)
