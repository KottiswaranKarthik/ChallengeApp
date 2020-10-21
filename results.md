# Overview

# Approach:
1. I am deploying this solutions using Azure DevOps to Azure environment and created service connection using service proncipal to be able to authenticate to my Azure subscription.
2. I have created an azure build and release pipeline to do the following activites using the yaml file. 
    - Yaml file Location: https://github.com/KottiswaranKarthik/ChallengeApp/blob/main/azure-pipelines.yaml
    - Create or Update Azure Container Registry
    - Build a Container image using the docker file
    - Push the image to Azure Container Registry
    - Create or Update Azure Container Instance
3. I have used azure resource manager template to create Azure Container registry and container instance.
    - ArmTemplate Location: https://github.com/KottiswaranKarthik/ChallengeApp/tree/main/ArmTemplate

# Build
1. The automated build pipeline will start once changes are committed to master/main branch.
2. For every build the image will be tagged with the corresponding build number.
3. The arm templates will be pushed to the publish folder to be consumed in release pipeline.
4. The image will be push to Azure container registry.
3. Azure Container Instance will pull latest build number tagged with the image from azure container registry.

# Release
1. Azure release pipeline will deploy the package to azure subscription.

# Output:
1. Servian Page
![ServianPage](https://github.com/KottiswaranKarthik/ChallengeApp/blob/main/ArmTemplate/Screenshots/Servian%20Page.png)
2. Swagger
![Swagger](https://github.com/KottiswaranKarthik/ChallengeApp/blob/main/ArmTemplate/Screenshots/Swagger.png)
3. Azure DevOps. Automated build and release successful deployment.
![AzureDevOps](https://github.com/KottiswaranKarthik/ChallengeApp/blob/main/ArmTemplate/Screenshots/Azure%20DevOps.png)
4. Azure Container Registry. Image and tagged with build number.
![AzureContainerRegistry](https://github.com/KottiswaranKarthik/ChallengeApp/blob/main/ArmTemplate/Screenshots/Azure%20Container%20Registry.png)
5. Azure Container Instance running the images.
![AzureContainerInstance](https://github.com/KottiswaranKarthik/ChallengeApp/blob/main/ArmTemplate/Screenshots/Azure%20Container%20Instance.png)


