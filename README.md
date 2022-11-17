# Installation and Deployment of terraform servers.
This tutorial would guide us about introduction of terraform.we shall discuss the following:- 
1. Deploy a single server
2. Deploy a single web server
3. Deploy a configurable web server
4. Deploy a cluster of web servers
5. Deploy a load balancer
6. Clean up

we should must read first this [tutorial](https://blog.gruntwork.io/an-introduction-to-terraform-f17df9c6d180#a9b0) and the code is explained in this 
[video part1](https://shorthillstech-my.sharepoint.com/personal/kapil_jain_shorthillstech_com/_layouts/15/onedrive.aspx?ga=1&id=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2F2022%2F44%2Fterraformfirst%20project%20%28part1%29%2Emp4&parent=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2F2022%2F44) and [video part2](https://shorthillstech-my.sharepoint.com/personal/kapil_jain_shorthillstech_com/_layouts/15/onedrive.aspx?ga=1&id=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2F2022%2F44%2FTerraform%20Deployment%5F%20kaumudi%20%2Emp4&parent=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2F2022%2F44) to know the steps properly:-

 # Installation /Fundamentals of terraform:-
 * Install Terraform and AWS account [video](https://shorthillstech-my.sharepoint.com/personal/kapil_jain_shorthillstech_com/_layouts/15/onedrive.aspx?ga=1&id=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2F2022%2F44%2Fterraformfirst%20project%20%28part1%29%2Emp4&parent=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2F2022%2F44)
 * Deploy server and clean [video](https://shorthillstech-my.sharepoint.com/personal/kapil_jain_shorthillstech_com/_layouts/15/onedrive.aspx?ga=1&id=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2F2022%2F44%2FTerraform%20Deployment%5F%20kaumudi%20%2Emp4&parent=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2F2022%2F44)

# STEPS TO RUN THE CODE AFTER WE CONFIGURE AWS ACCOUNT AND TERRAFORM ON OUR VIRTUAL M/C:-
1.Run terraform init command.It initializes a working directory containing Terraform configuration files.

```sh
terraform init

```

2.Run terraform plan command.It creates an execution plan,which lets you preview the changes that Terraform plans to make to our infrastructure.

```sh
terraform plan

```

3.Run terraform graph command(show us the dependency graph)

```sh
 terraform graph

```

4. Run terraform apply command. It perform the plan

```sh
terraform apply

```
    
5. Run curl http://<EC2_INSTANCE_PUBLIC_IP>:8080(to know the output ip address running status)

```sh
curl http://<EC2_INSTANCE_PUBLIC_IP>:8080

```
    
6. Run terraform destroy command. It terminate the machine

```sh
terraform destroy

```

# DEPLOYMENT:-
Remove code from line no. 14 to 29 .
![Screenshot (783)](https://user-images.githubusercontent.com/109335469/202369101-b0006c43-b0eb-4932-9212-b56763f8d8bd.png)


# Deploy a single server
1.Run the following commands:-

```sh
terraform init
terraform plan
terraform apply
terraform destroy
```
# Deploy a single web server
1.Make change in main.tf
![Screenshot (773)](https://user-images.githubusercontent.com/109335469/201565602-f8bc8458-2b31-4502-8330-81a07e294a98.png)

2.Run below commands:
```sh
terraform init
terraform plan
terraform apply
terraform destroy
```

3.Go to your aws instance and you’ll see your new EC2 Instance deploying. Click your new Instance, copy its public IP address in the description panel at the bottom of the screen. Give the Instance a minute or two to boot up, and then use a web browser or a tool like curl to make an HTTP request to this IP address at port 8080. Run below commands.
```sh
curl http://<EC2_INSTANCE_PUBLIC_IP>:8080
   terraform destroy
```
# Deploy a configurable web server
1.Add below code in main.tf
![Screenshot (774)](https://user-images.githubusercontent.com/109335469/201566138-53e36ccb-4dec-4ca8-b30f-79df3c233380.png)

2.Run following commands:-
```sh
terraform init
terraform plan
terraform apply
terraform destroy
```
# Deploy a cluster of web servers
1.Add following codes in main.tf
![Screenshot (775)](https://user-images.githubusercontent.com/109335469/201566491-0c4c86e2-f481-42b6-9710-ad767531bc1a.png)

2.Run following commands:-
```sh
terraform init
terraform plan
terraform apply
terraform destroy
```
# Deploy a load balancer
1.Add following code in main.tf
![Screenshot (776)](https://user-images.githubusercontent.com/109335469/201566885-dc97d5bc-1040-49d4-875f-fd79b15e9647.png)
![Screenshot (777)](https://user-images.githubusercontent.com/109335469/201567038-b2c15899-9b32-4b20-9fce-ddb6248bec47.png)
![Screenshot (778)](https://user-images.githubusercontent.com/109335469/201567147-32a57efb-2a15-48da-8c93-bac6f0c92571.png)

2.Run  the following commands:-
```sh
terraform init
terraform plan
terraform apply
terraform destroy
```
3.After running terraform apply we got a url in alb_dns_name outputs.Run below commands.


```sh
   Run curl http://<alb_dns_name>
   terraform destroy
```
