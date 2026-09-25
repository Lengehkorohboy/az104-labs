## Lab 02 - Storage

## Overview

This lab focuses on deploying and managing Azure Storage resources. The objective is to understand how to create storage accounts, configure storage services, implement data protection, manage access, and secure storage resources.

## Learning Objectives

By completing this lab, I was able to:

Create and configure Azure Storage Accounts
Manage Blob Containers
Configure File Shares
Implement Storage Account security
Configure lifecycle management policies
Manage storage access with RBAC and SAS tokens
Configure replication and redundancy options

## Skills Covered

- Task 1: Create and configure a storage account.
- Task 2: Create and configure secure blob storage.
- Task 3: Create and configure secure Azure file storage.

## Azure Services Used

Azure Storage Account
Azure Blob Storage
Azure Files

## Architecture diagram

## Prerequisites

Active Azure Subscription
Contributor Role on Subscription or Resource Group
Azure Portal Access
Azure CLI Installed
Azure PowerShell Installed

## Lab Environment

## Tasks

## Task 1: Create and configure a storage account

In this task, you will create and configure a storage account. The storage account will use geo-redundant storage and will not have public access.

1. Sign in to the **Azure portal** - `https://portal.azure.com`.

1. Search for and select `Storage accounts`, select **Storage accounts** in the results, and then click **+ Create**.
1. On the **Basics** tab of the **Create a storage account** blade, specify the following settings (leave others with their default values):

   | Setting | Value |

   | Subscription | Azure Subscription 1 |
   | Resource group | az104-rg|
   | Storage account name | az104freetown |
   | Region | (US) East US |
   | Performance | Standard |
   | Preferred storage type |Azure Blob Storage or Azure Data Lake Storage|
   | Redundancy | Geo-redundant storage|
   | Make read access to data available in the event of regional unavailability.

1. On the **Advanced** and **Security** tabs, use the informational icons to learn more about the choices. Take the defaults.
1. On the **Networking** tab, in the **Public network access** section, select **Disable**. This will restrict inbound access while allowing outbound access.

1. Review the **Data protection** tab. Notice 7 days is the default soft delete retention policy. Note you can enable versioning for blobs. Accept the defaults.

1. Review the **Encryption** tab. Notice the additional security options. Accept the defaults.

1. Select **Review + create**, wait for the validation process to complete, and then click **Create**.

1. Once the storage account is deployed, select **Go to resource**.

1. Review the **Overview** blade and the additional configurations that can be changed. These are global settings for the storage account. Notice the storage account can be used for Blob containers, File shares, Queues, and Tables.

1. In the **Security + networking** blade, select **Networking**. Notice **Public network access** is disabled.
   - Under Public network access, click **Manage** to open the Public network access configuration blade.
   - Set **Public network access** to **Enabled**. Set **Public network access scope** to **Enable from selected networks**.
   - In the **Resource settings: Virtual networks, IP Addresses and exceptions** section, Add your client IPv4 address.
   - Save your changes. If an informational banner appears suggesting you associate a network security perimeter, you can disregard it and continue.

1. In the **Data management** blade, select **Redundancy**. Notice the information about your primary and secondary data center locations.

1. In the **Data management** blade, select **Lifecycle management**, and then select **Add a rule**.
   - **Name** the rule `Movetocool`. Notice your options for limiting the scope of the rule. Click **Next**.
   - On the **Add rule** page, _if_ base blobs were last modified more than `30` days ago _then_ **Move to cool storage**. Notice your other choices.
   - Notice you can configure other conditions. Select **Add** when you are done exploring.

   ![Screenshot move to cool rule conditions.](../Screenshots/az104-lab02-movetocool.png)

## Task 2: Create and configure secure blob storage

In this task, you will create a blob container and upload an image. Blob containers are directory-like structures that store unstructured data.

### Create a blob container and a time-based retention policy

1. Continue in the Azure portal, working with your storage account.

1. In the **Data storage** blade, select **Containers**.

1. Click **+ Add container** and **Create** a container with the following settings:

   | Setting             | Value                                     |
   | ------------------- | ----------------------------------------- |
   | Name                | `freetowndata`                            |
   | Public access level | Notice the access level is set to private |

   ![Screenshot of create a container.](../Screenshots/azlab104-lab02-create-container.png)

1. On your container, scroll to the ellipsis (...) on the far right, select **Access policy**.

1. If a warning appears stating that authorization with Shared Key is disabled for the account, you can disregard it and continue.

1. In the **Immutable blob storage** area, select **Add policy**, change the type from **Legal hold** to **Time-based retention**.

   | Setting                  | Value                    |
   | ------------------------ | ------------------------ |
   | Policy type              | **Time-based retention** |
   | Set retention period for | `180` days               |

1. Select **Save**.

### Manage blob uploads

1. In the storage account's left menu, under **Settings**, select **Configuration** and set **Allow storage account key access** to **Enabled**, then click **Save**.

1. Next, navigate to **Access Control (IAM)**, click **Add role assignment**, select the **Storage Blob Data Contributor** role, and assign it to your user account, then click **Review + assign**.

1. Next, do the same steps as in the previous step to assign the **Storage File Data Privileged Contributor** role.

1. Once access is configured, select your **data** container and then click **Upload**.

1. On the **Upload blob** blade, expand the **Advanced** section.

   | Setting             | Value                                    |
   | ------------------- | ---------------------------------------- |
   | Browse for files    | add the file you have selected to upload |
   | Select **Advanced** |                                          |
   | Blob type           | **Block blob**                           |
   | Block size          | **4 MiB**                                |
   | Access tier         | **Hot** (notice the other options)       |
   | Upload to folder    | `securitytest`                           |
   | Encryption scope    | Use existing default container scope     |

1. Click **Upload**.

1. Confirm you have a new folder, and your file was uploaded.

1. Select your upload file and review the ellipsis (...) options including **Download**, **Delete**, **Change tier**, and **Acquire lease**.

1. Select the uploaded file to open its Overview panel, then copy the URL using the **Copy to clipboard** button in the Properties table. Paste the URL into a new **InPrivate** browser window.

1. You should be presented with an XML-formatted message stating **ResourceNotFound** or **PublicAccessNotPermitted**.

   > **Note**: This is expected, since the container you created has the public access level set to **Private (no anonymous access)**.

### Configure limited access to the blob storage

1. Browse back to the file that you uploaded and select the ellipsis (…) to the far right, then select **Generate SAS**.

1. Note the warning banner stating that authorization with Shared Key is disabled for this account — this means the Account key signing option will be unavailable.

1. Specify the following settings (leave others with their default values):Browse back to the file that you uploaded and select the ellipsis (…) to the far right, then select **Generate SAS** and specify the following settings (leave others with their default values):

   | Setting              | Value                                |
   | -------------------- | ------------------------------------ |
   | Signing method       | **User delegation key**              |
   | Permissions          | **Read** (notice your other choices) |
   | Start date           | yesterday's date                     |
   | Start time           | current time                         |
   | Expiry date          | tomorrow's date                      |
   | Expiry time          | current time                         |
   | Allowed IP addresses | leave blank                          |

1. Click **Generate SAS token and URL**.

1. Copy the **Blob SAS URL** entry to the clipboard.

1. Open another InPrivate browser window and navigate to the Blob SAS URL you copied in the previous step.

   > **Note**: You should be able to view the content of the file.

## Task 3: Create and configure an Azure File storage

In this task, you will create and configure Azure File shares. You will use Storage Browser to manage the file share.

### Create the file share and upload a file

1. In the Azure portal, navigate back to your storage account, in the **Data storage** blade, click **Classic file shares**.

1. Click **+ Classic file share** and on the **Basics** tab give the file share a name, `freetownshare1`.

1. Notice the **Access tier** options. Keep the default **Transaction optimized**.
1. Move to the **Backup** tab and ensure **Enable backup** is **not** checked. We are disabling backup to simplify the lab configuration.

1. Click **Review + create**, and then **Create**. Wait for the file share to deploy.

1. After the file share is created, an informational banner will appear prompting you to enable backup — you can disregard this message and continue.

   ![Screenshot of the create file share page.](../Screenshots/az104-lab02-create-share.png)

### Explore Storage Browser and upload a file

1. Return to your storage account and select **Storage browser**. The Azure Storage Browser is a portal tool that lets you quickly view all the storage services under your account.

1. Select **Clasic file shares** and verify your **share1** directory is present.

1. Select your **share1** directory and notice you can **+ Add directory**. This lets you create a folder structure.

1. If you see an authorization error, select **Switch Azure AD Account** (or change the authentication method to **Microsoft Entra user account**) in the Storage browser toolbar.

1. Select **Upload**. Browse to a file of your choice, and then click **Upload**.

### Restrict network access to the storage account

1. In the portal, search for and select **Network foundation**.

1. Under `Virtual networks` click **Create**. On the Basics tab, set **Resource group** as `az104-rg` and give the virtual network a **name**, `vnet1`.

1. Take the defaults for other parameters, select **Review + create**, and then **Create**.

1. Wait for the virtual network to deploy, and then select **Go to resource**.

1. In the **Settings** section, select the **Service endpoints** blade.
   - Select **Add**.
   - In the **Service** drop-down select **Microsoft.Storage**.
   - Leave the **Service endpoint policies** dropdown at its default of **0 selected**.
   - In the **Subnets** drop-down check the **Default** subnet.
   - Click **Add** to save your changes.

1. Return to your storage account.

1. In the **Security + networking** blade, select **Networking**.

1. Under **Public network access** select **Manage**.

1. Select **Add a virtual network** and then **Add existing network**.

1. Select **vnet1** and **default** subnet, select **Add**.

1. In the **IPv4 Addresses** section, **Delete** your machine IP address. Allowed traffic should only come from the virtual network.

1. Be sure to **Save** your changes.

   > **Note:** The storage account should now only be accessed from the virtual network you just created.

1. Select the **Storage browser** and **Refresh** the page. Navigate to your file share or blob content.

   > **Note:** You should receive a message _not authorized to perform this operation_. You are not connecting from the virtual network. It may take a couple of minutes for this to take effect. You may still be able to view the file share, but not the files or blobs in the storage account.

![Screenshot unauthorized access.](../Screenshots/az104-lab02-notauthorized.png)

- Provide an Azure PowerShell script to create a storage account with a blob container.
- Provide a checklist I can use to ensure my Azure storage account is secure.
- Create a table to compare Azure storage redundancy models.

## Learn more with self-paced training

- [Guided Project - Azure Files and Azure Blobs](https://learn.microsoft.com/training/modules/guided-project-azure-files-azure-blobs/). Practice storing business data securely by using Azure Blob Storage and Azure Files.
- [Create an Azure Storage account](https://learn.microsoft.com/training/modules/create-azure-storage-account/). Create an Azure Storage account with the correct options for your business needs.
- [Manage the Azure Blob storage lifecycle](https://learn.microsoft.com/training/modules/manage-azure-blob-storage-lifecycle). Learn how to manage data availability throughout the Azure Blob storage lifecycle.

## Key takeaways

Congratulations on completing the lab. Here are the main takeaways for this lab.

- An Azure storage account contains all your Azure Storage data objects: blobs, files, queues, and tables. The storage account provides a unique namespace for your Azure Storage data that is accessible from anywhere in the world over HTTP or HTTPS.
- Azure storage provides several redundancy models including Locally redundant storage (LRS), Zone-redundant storage (ZRS), and Geo-redundant storage (GRS).
- Azure blob storage allows you to store large amounts of unstructured data on Microsoft's data storage platform. Blob stands for Binary Large Object, which includes objects such as images and multimedia files.
- Azure file Storage provides shared storage for structured data. The data can be organized in folders.
- Immutable storage provides the capability to store data in a write once, read many (WORM) state. Immutable storage policies can be time-based or legal-hold.
