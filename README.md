# Como-Fazer-o-Deploy-de-uma-API-na-Nuvem-na-Pratica

Sample workflow to build and deploy a Node.js app to Containerized WebApp using publish profile

Webapps deploy Actions is supported for the Azure public cloud as well as Azure government clouds ('AzureUSGovernment' or 'AzureChinaCloud') and Azure Stack ('AzureStack') Hub. Before running this action, login to the respective Azure Cloud using Azure Login by setting appropriate value for the environment parameter.

Configure deployment credentials:
For any credentials like Azure Service Principal, Publish Profile etc add them as secrets in the GitHub repository and then use them in the workflow.

The above example uses app-level credentials i.e., publish profile file for deployment.

Follow the steps to configure the secret:

Note: As of October 2020, Linux web apps will need the app setting WEBSITE_WEBDEPLOY_USE_SCM set to true before continuing with next step of downloading the publish profile. This requirement will be removed in the future.
Download the publish profile for the WebApp from the portal (Get Publish profile option)
While deploying to slot, download the publish profile for slot. Also specify the slot-name field with the name of the slot.
Define a new secret under your repository settings, Add secret menu
Paste the contents for the downloaded publish profile file into the secret's value field
Now in the workflow file in your branch: .github/workflows/workflow.yml replace the secret for the input publish-profile: of the deploy Azure WebApp action (Refer to the example above)
