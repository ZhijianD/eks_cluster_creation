Provision EKS with Terraform

Steps to follow: 
(1) Make sure you are in a Linux environment with aws-cli, terraform, kubectl installed \n
(2) Setup AWS IAM user access key and secret access key \n
(3) Use 'aws configure' to setup aws-cli \n
(4) Set regions where you want to deploy the cluster in variables.tf OR create .tfvars file to specify variables \n
(5) Check main.tf to make sure tags are correct, you can specify tags as a variable in variable.tf too \n
(5) Call 'terraform init' \n
(6) Use 'terraform plan' to see if the script is correct \n
(7) If 'terraform plan' returns no error, then use 'terraform apply' to apply the changes planned. Wait for ~10min. \n
(8) In terminal, use 'aws eks --region ${region} update-config --name ${cluster_name}' to set context for kubectl. Remember to set environment variables before calling this \n
(9) Now the cluster should be working and we can check its status using 'kubectl cluster-info' and 'kubectl get nodes' \n
(10) We can also check nodes and EKS cluster in AWS console \n
(11) After we are done, remember to delete cluster using 'terraform destroy' \n
