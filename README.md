# Hub-Spoke

dfsdfasdfasd


## Installation

Use the Deploy to Azure button below. Note that the template will take about 2 hour to fully deploy.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FBorg-GitHub%2FHub-Spoke%2Fmain%2FTemplates%2Ftemplate.json)

**The template allows for the following parameters**
* sharedServicesSubId - The subscription id of the subscription to deploy the Shared Services resources to
* transitServicesSubId - The subscription id of the subscription to deploy the Transit resources to
* workloadSubId - The subscription id of the subscription to deploy the Workload resources to 
* adDomainName - The DNS domain name assigned to the Active Directory domain.
* adNetBiosName - The NetBIOS name assigned to the Active Directory domain.
* location - The region the resources will be provisioned to.
* keyVaultAdmin - The object id of the user or group security principal that will be the administrator of the Key Vault. Note that the permissions assigned to the security principal exclude destructive permissions such as purge. Review the permissions in the /templates/general/deploy-keyvault.json template for a detailed list of the permissions.
* vmAdminUsername - The username for the local administrators of the two virtual machines provisioned. This will also be the name of the built-in Domain Administrator in the Active Directory domain.
* vmAdminPassword - The password assigned to the local administrator account of the virtual machines, the Active Directory domain administrator account, and the sample Active Directory user accounts. You can change these later on to improve the security posture of the environment. This must be supplied as a secure string.

<img src=hub-spoke.png>
