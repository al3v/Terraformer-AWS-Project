# Terraformer-AWS-Project

This project offers a guide and scripts for using Terraformer to import your existing AWS infrastructure into Terraform configuration files. Terraformer is a CLI tool that generates tf/json and tfstate files based on existing infrastructure (reverse Terraform). This process allows for a seamless transition to managing your infrastructure as code using Terraform



![Animation](https://github.com/al3v/Terraformer-AWS-Project/assets/73062283/bebb0304-adc9-424d-b600-a5efc9eba729)


<br/><br/>

## Prerequisites 🧰
✅ **AWS CLI:** Make sure you have the [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-version.html) installed and configured with the necessary access rights to your AWS resources.  
✅ **Terraform:** Ensure you have [Terraform](https://developer.hashicorp.com/terraform/install) installed on your machine. Terraform is required to manage the generated files and apply changes.  

<br/><br/>

## Installation 🐾
### Installing Terraformer💫
1) After installing Terraform, Download exe file for the required cloud provider from [here](https://github.com/GoogleCloudPlatform/terraformer/releases). In our case, it is windows amd64.  
*source: https://github.com/GoogleCloudPlatform/terraformer/tree/master?tab=readme-ov-file#installation*

2) Add the path to the Terraformer executable file to the environmental variables' "Path" variable on your local system.


  <img src="https://github.com/al3v/Terraformer-AWS-Project/assets/73062283/da5dbf81-4c8b-4a4e-b59b-4f69c35cc20d" align="left"  width="60%"/> <img src="https://github.com/al3v/Terraformer-AWS-Project/assets/73062283/67a48b8d-416e-4de2-af27-60b75949b833" align="right"  width="35%"/>

  <br/><br/>
    <br/><br/>
      <br/><br/>
        <br/><br/>
          <br/><br/>
            <br/><br/>
              <br/><br/>
            
3) Create a folder📂(AWS to Terraform) and within it, create a file  named "version.tf"📄 to install the plugins required for your platform. For example, in our case we need plugins for the AWS Cloud so versions.tf should contain:

```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = ">= 5.41.0"
    }
  }
  required_version = ">= 0.13"
}
```
or
git clone this repo
```markdown
git clone https://github.com/al3v/Terraformer-AWS-Project.git
```

4) Configure AWS CLI 
```markdown
 aws configure
```
![image](https://github.com/al3v/Terraformer-AWS-Project/assets/73062283/2e21bca0-1628-47aa-ac70-4cfe530b28ce)

5) Navigate into the folder and ensure that the version.tf file is present

![image](https://github.com/al3v/Terraformer-AWS-Project/assets/73062283/c64c36be-eab8-4a49-a06a-0304cf0304d1)

6) Run 🖱️
```markdown
 terraform init
```
![image](https://github.com/al3v/Terraformer-AWS-Project/assets/73062283/1dc6fbcc-70c2-4d25-a7e7-230d3dc629b1)

7) Run 🖱️( [Here](https://github.com/GoogleCloudPlatform/terraformer/blob/master/docs/aws.md) are alternative commands you can use)
```markdown
 terraformer import aws --resources=vpc,subnet --regions=eu-west-1
```
![image](https://github.com/al3v/Terraformer-AWS-Project/assets/73062283/3cbc77f6-96a5-4d72-96d6-f253868401ba)


## Result ✨
In your folder(AWS to Terraform), you will find a subfolder named generated where you can locate separate subfolders for your "vpc.tf" and "subnet.tf" files.

![image](https://github.com/al3v/Terraformer-AWS-Project/assets/73062283/dc83b7f1-98d9-4dff-b1c9-2ac80d078da4)

