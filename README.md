# DevopsTest
# VM DEPLOYMENT USING AZURE DEVOPS PIPELINE
#  1-We will create a key vault, from the Azure portal, to store the VM password. 

  #   2-We will configure access policy for template deployment.


 #   3-We will retrieve the password in ARM template using the Key vault resource ID .




# 4- Push the code to the github registory for the use of azure devops pipeline.



# 5- Create the Organization in the Azure Devops Services.

# 6- Create the Project 

# 7- Create CI Pipeline

    #a-Get the Source code from the Git repository
    #b-Add the task to Copy the *.json file.
    #c-Add another task to publish the artifacts for the release pipeline.
# 8-Next we need to run the CI pipeline to generate the artifacts.

# 9-Create the Release pipeline .

     #a-Create task to deploy the Vnet 
     #b-Create task to deploy the VM
     #c-Here we need to integrate Azure key vault to pass the Admin Password because we did put the password in our script .
     #d-Create Variable group to integrate the azure key vault .
     #e-From this point, whatever variables you have in your variable group can be accessed from your build pipe as $(VariableNameHere)


#########################################################################################
#  WEPAPI DEPLOYMENT

#  1- Create a service principle 
      az ad sp create-for-rbac --skip-assignment
      From output note the "appId": "xxxxxxx","password": "xxxxxxxxxxx"
#  2- Create the Azure Container Registory 
#  3- Add role assignment (AcrPull) while role assignment use the service principle appId which we create at point 1
#  4-Create the AKS cluster and use here SP as well(use appId,Password)
--------------------------------------------------------------------------------------------
#  CI PIPELINE
# 1- Create CI pipeline for webapi build.
     # Add the CI task related to the webapi build
     # Task-01: Add the task to build the image using th dockerfile:
     #  Here we need to need to create the connection between ACR and pipeline and select the container repository.
   
# Task02: -Image push to ACR
# Task03:-Update the latest build image using the replacement token task.
          # Here latest build image will update in the deployment file “WebApi-Deployment.yaml” using the token prefix
# Task04: Copy the Artifacts
# Task05: Publish the artifact for the release pipeline .

----------------------------------------------------------------------------
# Release Pipeline:
    Next Step we have to create the release pipeline using the CI artifact . In the release pipeline we have to select job as Deploy to Kubernetes.
    Since we have to two definition file on is for the Deployment and other is for the Service.So, we have to create two task 

    Task01: One you add the task then we have to authenticate with the azure portal and need to specify in which name-space.
            we want to deploy and we need to choose the command for the action so, here we will select “apply” and we will provide the
            Deployment file location.
    Task02 : Same thing we have to for the Service as well .Once you have done this then you are ready for the release .


