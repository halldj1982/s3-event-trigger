### IMPORTANT
* Use standard source control best practices: Modify locally and check in your changes before deploying terraform and/or Lamda code
* If you are changing the Lambda code, make sure to redo the src.zip file in the root directory by zipping the whole "src" directory as this is what is deployed, not the .py file
* Terraform commands must be run in the "infra" directory. It will pick up the src.zip in the root directory when terraform apply is run.


### Lambda S3 Notifier

Steps:
* Run `terraform init` to initialize terraform in the infra folder
* fill in the missing values in the `terraform.tfvars` file
* NOTE: If the AWS SES sandbox is being used ensure the email addresses are verifed
* run  `terraform apply -var-file=terraform.tfvars` to build infrastructure on the AWS environment
* To destroy infrastructure run `terraform destroy -var-file=terraform.tfvars` to destroy all running infrastructure on AWS
