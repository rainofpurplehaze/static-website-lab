## Lab 01 - Building a Static Website
This lab is about creating a website using Microsoft Azure without using a virtual machine. 

https://www.loom.com/share/ba355bd8c43941f0b486e1138aa426cf

## Create and Clean Up a Static Website in Microsoft Azure Using Blob Storage

### Objective

This explains how to create a static website in Microsoft Azure using a resource group and storage account, upload the website files, verify the site through the generated endpoint, and then clean up all resources to avoid unnecessary charges.

### Key Steps

 

**1. Create a new resource group** [0:20](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=20)

![generated-image-at-00:00:20](https://loom.com/i/1d0eeeb215c6468da83a420c44974ff0?workflows_screenshot=true)

- In the Azure portal, go to **Resource groups** and select **Create**.
- Confirm the correct **subscription** is selected.
- Enter a unique resource group name, such as `rg-jabari`.
- Set the region to **East US**.
- Leave all other settings at default.
- Select **Review + create**, verify the details, then select **Create**.

 

**2. Confirm the resource group was created** [1:29](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=89)

![generated-image-at-00:01:29](https://loom.com/i/70f994e14a75417f8fffaa2425e6d770?workflows_screenshot=true)

- Return to the Azure home page.
- Open **Resource groups** and verify the new resource group appears in the list.
- Confirm the resource group is available before moving to the next step.

 

**3. Create a storage account inside the resource group** [1:56](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=116)

![generated-image-at-00:01:56](https://loom.com/i/4d0b2ea5c0e8445a9b80fbade5f73b60?workflows_screenshot=true)

- From the Azure home page, open **Storage accounts** and select **Create**.
- Confirm the **subscription** is correct.
- Select the resource group created in Step 1 so the storage account stays grouped with the project.
- Enter a unique storage account name, such as `StorageJibari`.
- Keep the region as **East US**.
- Set the primary service to **Azure Blob Storage**.
- Keep the performance tier as **Standard**.
- Keep replication as **Geo-redundant storage**.
- Leave networking, data protection, security, encryption, and tags at default values.
- Select **Review + create**, then select **Create** to start deployment.

 

**4. Wait for the storage account deployment to complete** [3:30](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=210)

![generated-image-at-00:03:30](https://loom.com/i/2e42fdec30364e36bf7003e8503ebde1?workflows_screenshot=true)

- Monitor the deployment status until it shows completion.
- Once deployment finishes, open the storage account resource to continue configuration.

 

**5. Enable static website hosting** [3:53](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=233)

![generated-image-at-00:03:53](https://loom.com/i/43b95f6c14d94d1fbc8a3b209e241c63?workflows_screenshot=true)

- In the storage account, go to **Data management** and select **Static website**.
- Change the static website setting from **Disabled** to **Enabled**.
- Enter `index.html` as the **Index document name**.
- Enter `error.html` as the **Error document path**.
- Select **Save** to create the static website configuration.

 

**6. Record the generated website endpoint and container** [4:43](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=283)

![generated-image-at-00:04:43](https://loom.com/i/754bf51b9f854d369ee9afec016b8e74?workflows_screenshot=true)

- After saving, note that Azure creates the `$web` container automatically.
- Record the **primary endpoint** and **secondary endpoint** shown by Azure.
- Use the primary endpoint as the main URL for testing the website.

 

**7. Upload the website file to the $web container** [5:11](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=311)

![generated-image-at-00:05:11](https://loom.com/i/3d1ec90f225c431f864edb7b8593a811?workflows_screenshot=true)

- Go to **Data storage** and select **Containers**.
- Open the `$web` container.
- Select **Upload**.
- Browse for the website file, such as `index.html`.
- Select **Upload** to place the file into the `$web` container.
- Confirm the file appears in the container after upload.

 

**8. Test the static website in a browser** [6:29](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=389)

![generated-image-at-00:06:29](https://loom.com/i/4458a983c4904e408fed0a29aead78bc?workflows_screenshot=true)

- Copy the **primary endpoint** from the static website settings.
- Open a new browser tab and paste the endpoint into the address bar.
- Press **Enter** to load the site.
- Verify the page displays the expected content, such as a greeting message and confirmation that the site is hosted on Azure Blob Storage.

 

**9. Delete the resource group and associated resources** [7:18](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=438)

![generated-image-at-00:07:18](https://loom.com/i/2c8b56bf1b6e43c7bb8c66d358b478dd?workflows_screenshot=true)

- After confirming the website works, return to the Azure home page.
- Open **Resource groups** and select the resource group created earlier.
- Choose **Delete resource group**.
- Type the resource group name exactly as requested to confirm deletion.
- Select **Delete** again to finalize the action.
- Wait for Azure to remove the resource group and all resources inside it, including the storage account.

 

**10. Verify cleanup is complete** [8:53](https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf?t=533)

![generated-image-at-00:08:53](https://loom.com/i/930e0cac60734e2ab7e335196496f6ab?workflows_screenshot=true)

- Refresh the Azure portal after a few minutes.
- Confirm the storage account is gone.
- Confirm the resource group is no longer listed.
- Ensure the environment is back to its original state and no unused resources remain.

### Cautionary Notes

- **Be careful when deleting the resource group:** this removes all resources inside it, including the storage account and static website configuration.
- **Double-check the subscription and region** before creating resources to avoid placing them in the wrong environment.
- **Use the exact resource group name** when confirming deletion, or Azure will not proceed.
- **Remember that cloud resources can incur charges** if left running, even if they are no longer actively used.
- **Wait for deployment and deletion to fully complete** before moving to the next step.

### Tips for Efficiency

- Use a consistent naming convention, such as `rg-<name>` for resource groups and a clear unique name for storage accounts.
- Keep most settings at default unless your organization requires specific security, networking, or redundancy options.
- Save the primary endpoint immediately after enabling static website hosting so you can test the site quickly.
- Upload the website file directly to the `$web` container to avoid confusion with other storage containers.
- Clean up resources right after testing to prevent unnecessary costs and keep the Azure environment organized.

### Link to Loom

<https://loom.com/share/ba355bd8c43941f0b486e1138aa426cf>
