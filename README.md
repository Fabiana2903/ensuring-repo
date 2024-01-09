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

Once this is done, run the following command to create a packer image: 
```
packer build ./packer-image.json
```
![imagen](https://github.com/Fabiana2903/ensuring-repo/assets/149669704/7708a68b-db80-47af-aafb-61e3e30fb1e6)

![imagen](https://github.com/Fabiana2903/ensuring-repo/assets/149669704/bbb22a89-1dec-48d6-9dd4-c4f800233b9c)



## Suggestions and Corrections
Feel free to submit PRs to this repo should you have any proposed changes. 
