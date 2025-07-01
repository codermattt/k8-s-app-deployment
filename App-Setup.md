# Notes 
- used AWS ec2 instance as base machine, and AWS route53 as my DNS provider for DNS lookups
- GoDaddy domain (thedev-oper.space) was updated with the 4 NS records from Route53
  - Route53 is responsible for where the domain points
- The Tomcat (devopper000/vprofileapp) and the MySQL (devopper000/vprofileadb) public images were pulled from my Dockerhub
- An nginx ingress controller was used to create an AWS elastic Load Balancer

# Steps

 
