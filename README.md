# flask_5_tailwind

# Design Rationale and Principles Followed

# Setting Up and Using the CDN with your Flask App

1. Log into Azure account
2. Type in "Storage Account" into the search bar
3. Create a storage account
4. Adjust settings accordingly
- Performance: standard
- Redundancy: geo-redundant storage (GRS)
5. Click create button to create the storage account
6. Once storage account is created, navigate to the overview page for the storage account
7. Go to "Containers" in the navigation bar on left hand side
8. Click (+ container) button and choose access level and name the container
- Go to security in the overview page and enable "secure transfer required", "allow Blob anonymous access", and "allow storage account key access"
9. Create the container by clicking the create button
10. Click into the container and upload desired files
11. On the containers main page, click on "Front Door and CDN" in navigation bar on the left hand side of the page
12. Create a new endpoint
- Select Azure CDN
- Click "Create new"
- Give profile name, endpoint name (used for URL), origin host name
- Pricing tier: Standard Microsoft
- Query String Caching Behavior: Ignore query string
13. Navigate to containers page and click on the media uploaded earlier in step 10
14. Go to the URL and copy everything after the ".net"
15. Paste the portion copied from previous step at the end of the endpoint host name link + click enter
16. Copy the new host name link and paste into index_tailwind.html file in:

  ```<img src -insert new host name link ... >```

# Deploying your Flask App to the Chosen Cloud Platform

1. In the Google shell terminal, type in curl ```-sL https://aka.ms/InstallAzureCLIDeb | sudo bash```
2. Type in az.
3. Type in az login --use-device-code to connect a Microsoft Azure account to Google shell.
4. A separate window will open to a Microsoft page. Copy and paste the code from the Google shell into the Microsoft page and confirm that you want to authenticate. Once authentification is complete, you can go back to the Google shell terminal.
5. Type ```az account list --output table into the shell terminal```
6. Type ```az account set --subscription <subscriptionId>``` Replace "subscriptionId" with the subscriptionId under the desired account that was listed under the ```az account list --output table command```
7. Log into Azure Web Portal and create a new resource group.
8. In the Google shell terminal, type in ```az group list```
9. Type in ```az webapp up --name- <resource group> --flask --runtime PYTHON:3.9 --sku B1```
10. A resource group will be created and zip deployment will begin.
11. Go to App Services to track the deployment process.
12. Once deployment is complete, a link to the Azure domain will show on the App services page and in the Google shell terminal.

# Observations and Benefits of Using a CDN and Cloud Deployment

# Addressing Challenges Encountered
