---
services: data-factory
platforms: dotnet
author: spelluru
---
# Sample: copy data one folder to another folder in an Azure Blob Storage
In this sample you do the following steps by using .NET SDK:

1. Create a data factory.
2. Create a linked service to link your Azure Storage account to the data factory.
3. Create a dataset that represents input/output data used by the copy activity.
4. Create a pipeline with a copy activity that copies data. 

## Prerequisites

* **Azure subscription**. If you don't have a subscription, you can create a [free trial](http://azure.microsoft.com/pricing/free-trial/) account.
* **Azure Storage account**. You use the blob storage as **source** and **sink** data store. If you don't have an Azure storage account, see the [Create a storage account](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account) article for steps to create one. 
* Create a **blob container** in Blob Storage, create an input **folder** in the container, and upload some files to the folder. 
* **Visual Studio** 2015 Update 3, or 2017. The walkthrough in this article uses Visual Studio 2017.
* Download and install [Azure .NET SDK](http://azure.microsoft.com/downloads/).
* **Create an application in Azure Active Directory** following [this instruction](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal.md#create-an-azure-active-directory-application). Make note of the following values that you use in later steps: **application ID**, **authentication key**, and **tenant ID**. Assign application to "**Contributor**" role by following instructions in the same article.


## Build and run the sample

1. Click **Tools** -> **NuGet Package Manager** -> **Package Manager Console**.
2. In the **Package Manager Console**, run the following commands to install packages:

    ```
    Install-Package Microsoft.Azure.Management.DataFactory
    Install-Package Microsoft.Azure.Management.ResourceManager
    Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
    ```
3. Set values for variables in the Program.cs file: 

    ```csharp
    string tenantID = "<tenant ID>";
    string applicationId = "<application ID>";
    string authenticationKey = "<application key>";
    string subscriptionId = "<subscription ID>";
    string resourceGroup = "<resource group name>";
    string region = "East US";
    string dataFactoryName = "<data factory name>";
    string storageAccount = "<azure storage account name>";
    string storageKey = "<azure storage account key>";
    string inputBlobPath = "<blobcontainer/inputfolder>";
    string outputBlobPath = "<blobcontainer/outputfolder>"; 
    ```
4. Add some text files to the input folder in the Azure Blob Storage. 
5. Build the project and run the program.
6. Verify that the files are copied to the destination location in the Blob Storage. 

## See Also
For step-by-steps instructions to create this sample from scratch, see [Quickstart: create a data factory and pipeline using .NET SDK](https://docs.microsoft.com/en-us/azure/data-factory/quickstart-create-data-factory-dot-net).
 

