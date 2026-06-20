## Lab 01 - Building a Static Website
This lab is about creating a website using Microsoft Azure without using a virtual machine. 

https://www.loom.com/share/ba355bd8c43941f0b486e1138aa426cf

## Create and Clean Up a Static Website in Microsoft Azure Using Blob Storage

### Objective

This explains how to create a static website in Microsoft Azure using a resource group and storage account, upload the website files, verify the site through the generated endpoint, and then clean up all resources to avoid unnecessary charges.

<img width="2720" height="2480" alt="azure_static_website_architecture_v2" src="https://github.com/user-attachments/assets/16535243-642a-4eef-9f40-886b0056e017" />


### Key Steps



**1. Create a new resource group** 

<img width="468" height="322" alt="Create a new resource group" src="https://github.com/user-attachments/assets/87e7b894-5034-4f47-b29b-88c7e378c863" />


- In the Azure portal, go to **Resource groups** and select **Create**.
- Confirm the correct **subscription** is selected.
- Enter a unique resource group name, such as `rg-jabari`.
- Set the region to **East US**.
- Leave all other settings at default.
- Select **Review + create**, verify the details, then select **Create**.

 

**2. Confirm the resource group was created** 

<img width="468" height="322" alt="Confirm the resource group was created" src="https://github.com/user-attachments/assets/bb4ea3b9-7da3-4a41-a5d4-58ba54032bfa" />


- Return to the Azure home page.
- Open **Resource groups** and verify the new resource group appears in the list.
- Confirm the resource group is available before moving to the next step.

 

**3. Create a storage account inside the resource group** 

<img width="468" height="322" alt="Create as storage account" src="https://github.com/user-attachments/assets/83fe22a1-cadf-4c1a-a289-86cf25eec26b" />


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

 

**4. Wait for the storage account deployment to complete** 

<img width="468" height="322" alt="Wait for the storage account" src="https://github.com/user-attachments/assets/c0b8b65a-c8a8-46eb-b4b7-2af94a90ddf9" />

- Monitor the deployment status until it shows completion.
- Once deployment finishes, open the storage account resource to continue configuration.

 

**5. Enable static website hosting** 

<img width="468" height="322" alt="EnableStatichost" src="https://github.com/user-attachments/assets/0b75db6d-9369-44e6-8e84-19f13c730c6b" />


- In the storage account, go to **Data management** and select **Static website**.
- Change the static website setting from **Disabled** to **Enabled**.
- Enter `index.html` as the **Index document name**.
- Enter `error.html` as the **Error document path**.
- Select **Save** to create the static website configuration.

 

**6. Record the generated website endpoint and container** 

<img width="468" height="322" alt="Recordthegeneratedwebsite" src="https://github.com/user-attachments/assets/319bc88f-e89f-4d4c-b0a8-169369f424e0" />


- After saving, note that Azure creates the `$web` container automatically.
- Record the **primary endpoint** and **secondary endpoint** shown by Azure.
- Use the primary endpoint as the main URL for testing the website.

 

**7. Upload the website file to the $web container** 

<img width="886" height="610" alt="Image 6-19-26 at 6 43 PM" src="https://github.com/user-attachments/assets/a65002b6-9453-4d8e-a8e1-7ba16e7cf686" />


- Go to **Data storage** and select **Containers**.
- Open the `$web` container.
- Select **Upload**.
- Browse for the website file, such as `index.html`.
- Select **Upload** to place the file into the `$web` container.
- Confirm the file appears in the container after upload.

 

**8. Test the static website in a browser** 

<img width="468" height="322" alt="Websiteworks" src="https://github.com/user-attachments/assets/434ec327-b366-424a-a18c-057cbd0a53f0" />


- Copy the **primary endpoint** from the static website settings.
- Open a new browser tab and paste the endpoint into the address bar.
- Press **Enter** to load the site.
- Verify the page displays the expected content, such as a greeting message and confirmation that the site is hosted on Azure Blob Storage.

 

**9. Delete the resource group and associated resources** 

<img width="877" height="609" alt="Image 6-19-26 at 6 50 PM" src="https://github.com/user-attachments/assets/93353dcf-4117-4601-a607-95097219174f" />


- After confirming the website works, return to the Azure home page.
- Open **Resource groups** and select the resource group created earlier.
- Choose **Delete resource group**.
- Type the resource group name exactly as requested to confirm deletion.
- Select **Delete** again to finalize the action.
- Wait for Azure to remove the resource group and all resources inside it, including the storage account.

 

**10. Verify cleanup is complete** 

<img width="869" height="603" alt="Screenshot 2026-06-19 at 6 51 16 PM" src="https://github.com/user-attachments/assets/ce4ffb96-8056-4fee-9bf3-7cca5c086187" />


- Refresh the Azure portal after a few minutes.
- Confirm the storage account is gone.
- Confirm the resource group is no longer listed.
- Ensure the environment is back to its original state and no unused resources remain.

### Cautionary Notes

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
