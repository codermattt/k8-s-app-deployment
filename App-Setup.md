# Notes 
- I used AWS ec2 instance as my base machine, and AWS route53 as my DNS provider for DNS lookups
- GoDaddy domain (thedev-oper.space) was updated with the 4 NS records from Route53
  - Route53 is responsible for where the domain points
- The Tomcat (devopper000/vprofileapp) and the MySQL (devopper000/vprofileadb) public images were pulled from my Dockerhub
- A secrets file was used for the rabbitmq default password and the MySQL root password
- An nginx ingress controller was used to create an AWS elastic Load Balancer

# Steps
1. Create cluster on ec2 e.g "kops create cluster --name=kops.thedev-oper.space..., kops update cluster..."

2. Created controller
   - kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.1.3/deploy/static/provider/aws/deploy.yaml

3. Migrated manifest files from my local vs-code to the ec2 instance,  then deployed from the manifest files using kubectl.

4. Entered Domain name "vprofile.thedev-oper.space" as in appingress.yaml file on browser to verify the web app.

# Problem faced
- I am noting this because it took me very to solve.
- My rabbitmq default user and password in the manifest files did not match the configuration set up in the application.properties file of the web app, so it was not working for quite some.
- Stack overflow helped me out.

 
