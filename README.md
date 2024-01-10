# Project Starter
This repository contains the starter code for the **Ensuring Quality Releases** project of the cd1807 Ensuring Quality Releases (Quality Assurance) course taught by Nathan Anderson. 


## How to use?
- Fork this repository to your Github account and clone it locally for further development. 
- Follow the classroom instructions, and check the rubric before a submission.

## Dependencies 

These are the following dependencies and softwares that the user must have in order to complete this project:

- Azure CLI
- Terraform
- JMeter
- Postman
- Python
- Selenium
- Chromedriver
- Chrome

## Instructions 
These are the step by step process followed to complete this project: 

1. Log in to your Azure account. This can be achieved through your preferred terminal, such as the Command Prompt (cmd). Utilize the following command to log in:

```
az login 
```
2. Within this repository, we are utilizing Azure credentials provided by Udacity. Consequently, the Azure resource group "Azuredevops" is employed. Execute the Packer image for the virtual machine.

To begin, update the variables specified in the "packer-image.json" file. Replace the placeholder values with your actual information for:

- Subscription ID
- Tenant ID
- Client ID
- Client Secret
- Resource Group Name
- Image Name
- VM Size

```
    "subscription_id": "",
    "tenant_id": "",
    "client_id": "",
    "client_secret": "",   
    "resource_group_name": "",
    "image_name": "",
    "vm_size": ""
```

Once this is done, run the following command to create a packer image: 
```
packer build ./packer-image.json
```
![imagen](https://github.com/Fabiana2903/ensuring-repo/assets/149669704/7708a68b-db80-47af-aafb-61e3e30fb1e6)

![imagen](https://github.com/Fabiana2903/ensuring-repo/assets/149669704/bbb22a89-1dec-48d6-9dd4-c4f800233b9c)

3. Next, configure the storage account and state backend. Initially, run the script named "create-tf-storage.sh" using the following command:

```
bash configure-tfstate-storage-account.sh
```
![imagen](https://github.com/Fabiana2903/ensuring-repo/assets/149669704/c3d7d70e-371d-45ab-aff3-e039ecce15e8)

4. Then, replace the values in the "terraform/main.tf" file with the output obtained from running the "create-tf-storage.sh" script. Update the backend configuration in the "terraform.tfvars" file.

![imagen](https://github.com/Fabiana2903/ensuring-repo/assets/149669704/4a0cb48d-019d-4bf3-9f5c-4f33c04f476c)

Generate SSH keys in the Azure command shell using the commands:

```
ssh-keygen -t rsa
cat ~/.ssh/id_rsa.pub

```
Place the generated keys in "terraform/modules/vm/vm.tf" under the "admin_ssh_key" section.

5. Run Terraform

Use the following commands: 

```
terraform init
terraform validate
terraform apply
```
Your results should look somewhat like this
![image](https://github.com/Fabiana2903/ensuring-repo/assets/149669704/36bcd3c6-acc5-4742-934f-02e4fa6f07f3)


### Pipeline Development:

1. Create a new project.
2. Generate a Personal Access Token (PAT) and retain it for later use.
3. Establish a new service connection.
4. Create an agent pool with access to all pipelines and add this agent to a virtual machine.
5. Create an environment and assign it to a different virtual machine than the one used in the previous step.
6. Finally, create a new pipeline by selecting the GitHub repository, and for the YAML configuration, choose "azure-pipelines.yaml."


## Suggestions and Corrections
Feel free to submit PRs to this repo should you have any proposed changes. 
