# 🚀 Azure Web App Deployment (via GitHub Actions)

This project automatically deploys to Azure Web App using GitHub Actions whenever changes are pushed to the main branch.


# The deployment workflow is defined in:

.github/workflows/azure-webapps-node.yml

#  Setup Instructions

Create an Azure Web App

Go to Azure Portal

Create a new App Service → select Runtime: Node.js

Get Publish Profile

In the Azure Portal → your App Service → Deployment Center → Get publish profile

Download the .PublishSettings file.

Add Secrets to GitHub
Go to your repository → Settings → Secrets → Actions → New repository secret:

AZURE_WEBAPP_NAME → your app name (e.g., my-node-webapp)

AZURE_WEBAPP_PUBLISH_PROFILE → paste the content of your downloaded publish profile.

Deploy Automatically
Every push to main triggers:

'''bash
npm install
npm run build (if defined)


Then deploys the app to Azure.



In GitHub → Actions tab → you’ll see:

✅ Checkout repository
✅ Install dependencies
✅ Build (if available)
✅ Deploy to Azure Web App
