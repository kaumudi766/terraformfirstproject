#This task  guide about introduction of terraform . we know about following topics:-
1. Set up your AWS account
2. Install Terraform
3. Deploy a single server
4. Deploy a single web server
5. Deploy a configurable web server
6. Deploy a cluster of web servers
7. Deploy a load balancer
8. Clean up

you should must read first this blog to know the steps properly:-

*Install Terraform and AWS account (Video link is provided in comment of this task)
* Deploy server and clean (Video link is provided in comment of this task)

STEPS TO RUN THE CODE AFTER WE CONFIGURE AWS ACCOUNT ON OUR VIRTUAL M/C:-
1.Run terraform init command
     ~ terraform init
2.Run terraform plan command
     ~ terraform plan
3.Run terraform graph command(show us the dependency graph) 
    ~ terraform graph
4. Run terraform apply command
    ~ terraform apply
5. Run curl http://<EC2_INSTANCE_PUBLIC_IP>:8080(to know the output ip address running status)
    ~ curl http://<EC2_INSTANCE_PUBLIC_IP>:8080
6. Run terraform destroy command
   ~ terraform destroy
