# Postmortem

This postmortem is a scrutiny of a situation that I experienced

## Issue Summary

I develop an ecommerce system for a start up.  
The application handles the storefront, dashbaord,  checkout and payments using online gateways 
5 months after I finsh the development and deployed the servies on AWS.


## Timeline
**Nov 3rd 2019**

* 4:21pm: The traffic amount increased for no reason in the evening hours
and cpu time was high

**Nov 13th 2019**    
* The issue was detected when customers were purchasing on quick sales and  report that they can't checkout orders and paymants were slow 
 on the application portal.
* I was contacted by the CTO to check the issue.
* The action that I took was to review the cloudwatch logs for the apprunner services  located on AWS consoler.

**Nov 14th 2019**
* Scaled ther services to support more resources 



## Root Cause and Resolution
While I was checking the logs I found an unusual amount of traffic in the evening hours,
 
I can think this was due to big ecommerce webservice going down due to a hack and customers were shifting..

I also check that the app has enough bandwidth available, and everything is ok, the issue was that strange amount of traffic.

I had to scale up all the services we are running to accomodate this traffic.. 


## Correct and Preventative Measures

AWSs implements auto scale and traffic alter policies to make decisions whether to scale in specific senarios.
