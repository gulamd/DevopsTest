# DevopsTest
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
   #e-After this we need to pass the variable under the override template parameters.
   

