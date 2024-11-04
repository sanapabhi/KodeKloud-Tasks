# Azure CLI Commands

## Basic Commands

### Authentication and Login
- **`az login`**: Log in to your Azure account.
- **`az account set`**: Set your default subscription.
- **`az account show`**: Display information about the current account.

### Resource Groups
- **`az group create`**: Create a new resource group.
- **`az group list`**: List all resource groups.
- **`az group delete`**: Delete a resource group.
- **`az group show`**: Show details of a specific resource group.

### Virtual Machines
- **`az vm create`**: Create a new virtual machine.
- **`az vm list`**: List all virtual machines.
- **`az vm start`**: Start a virtual machine.
- **`az vm stop`**: Stop a virtual machine.
- **`az vm delete`**: Delete a virtual machine.

### Virtual Machine Scale Sets
- **`az vmss create`**: Create a virtual machine scale set.
- **`az vmss scale`**: Scale a virtual machine scale set.

### Storage Accounts
- **`az storage account create`**: Create a new storage account.
- **`az storage account list`**: List all storage accounts.
- **`az storage account delete`**: Delete a storage account.

### Blobs
- **`az storage blob upload-blob`**: Upload a blob to a storage account.
- **`az storage blob download-blob`**: Download a blob from a storage account.

### Files
- **`az storage file service create`**: Create a file share.
- **`az storage file upload-file`**: Upload a file to a file share.

### Virtual Networks
- **`az network vnet create`**: Create a new virtual network.
- **`az network vnet list`**: List all virtual networks.
- **`az network vnet delete`**: Delete a virtual network.

### Network Security Groups
- **`az network nsg create`**: Create a new network security group.
- **`az network nsg rule create`**: Create a new security rule.
- **`az network nsg rule list`**: List security rules.

### Public IP Addresses
- **`az network public-ip create`**: Create a public IP address.
- **`az network public-ip delete`**: Delete a public IP address.

### Load Balancers
- **`az network lb create`**: Create a load balancer.
- **`az network lb rule create`**: Create a load balancer rule.
- **`az network lb probe create`**: Create a health probe for the load balancer.

## Advanced Commands

### Azure Resource Manager (ARM) Templates
- **`az deployment group create`**: Deploy resources using an ARM template.
- **`az deployment group validate`**: Validate an ARM template.
- **`az deployment group what-if`**: Preview the changes that would be made by a deployment.

### Azure Functions
- **`az functionapp create`**: Create a new Azure Function app.
- **`az functionapp deploy`**: Deploy a function app.

### Azure App Service
- **`az webapp create`**: Create a new web app.
- **`az webapp deploy`**: Deploy a web app.

### Azure Kubernetes Service (AKS)
- **`az aks create`**: Create a new AKS cluster.
- **`az aks get-credentials`**: Get Kubernetes credentials.

### Azure Monitor
- **`az monitor log-query`**: Query Azure Monitor logs.
- **`az monitor alert create`**: Create a new alert.
- **`az monitor alert list`**: List all active alerts.

## Production-Level Commands

### Azure Automation
- **`az automation runbook create`**: Create a new runbook.
- **`az automation job schedule`**: Schedule a runbook job.
- **`az automation job list`**: List all runbook jobs.

### Azure Policy
- **`az policy assignment create`**: Assign a policy to a resource group.
- **`az policy definition create`**: Create a new policy definition.

### Azure Backup
- **`az backup protection enable-for-vm`**: Enable backup for a VM.
- **`az backup restore restore-disks`**: Restore disks from a backup.

### Azure Site Recovery
- **`az site-recovery replication-group create`**: Create a replication group.
- **`az site-recovery replication-group failover`**: Failover a replication group.

## Security and Compliance Commands

### Azure Security Center
- **`az security center assessment list`**: List security assessments for your subscriptions.
- **`az security center policy assignment create`**: Assign a security policy to a resource group.

### Azure Key Vault
- **`az keyvault create`**: Create a key vault to store secrets.
- **`az keyvault secret set`**: Set a secret in a key vault.

### Azure Active Directory
- **`az ad sp create-for-rbac`**: Create a service principal for RBAC.
- **`az ad group create`**: Create an Azure AD group.

### Azure Blueprints
- **`az blueprint definition create`**: Create a blueprint definition.
- **`az blueprint assignment create`**: Assign a blueprint to a scope.

## Troubleshooting Commands

### Azure CLI
- **`az --version`**: Check the Azure CLI version.
- **`az account show`**: Show the current account information.
- **`az group show`**: Show information about a resource group.
- **`az vm show`**: Show information about a virtual machine.

### Azure Resource Manager
- **`az deployment group show`**: Show information about a deployment.
- **`az deployment group validate`**: Validate an ARM template.

### Azure Monitor
- **`az monitor log-query`**: Query logs for troubleshooting.
- **`az monitor alert list`**: List active alerts.

---

### Additional Tips
- **Use Azure CLI Extensions**: Install and use extensions to extend the functionality of the Azure CLI.
- **Leverage the `--help` Flag**: Use the `--help` flag to get detailed information about a specific command.
- **Optimize with Azure Advisor**: Use recommendations to optimize cost, performance, and security.
- **Utilize Azure Resource Graph**: Query and analyze your Azure resources using Resource Graph.
- **Explore Azure Portal**: The Azure portal provides a visual interface for managing and troubleshooting resources.

By mastering these Azure CLI commands, you can efficiently manage, optimize, secure, and troubleshoot your Azure infrastructure.
# Azure CLI Commands

## Core Commands

### Authentication and Account Management
- **`az login`**: Log in to Azure.
- **`az logout`**: Log out of Azure.
- **`az account set --subscription <subscription-id>`**: Set the default subscription.
- **`az account list-locations`**: List all Azure regions.

### Resource Groups
- **`az group create --name <group-name> --location <location>`**: Create a new resource group.
- **`az group list`**: List resource groups.
- **`az group delete --name <group-name>`**: Delete a resource group.

### Tagging Resources
- **`az tag create --name <tag-name>`**: Create a tag.
- **`az tag add-value --name <tag-name> --value <tag-value>`**: Add a tag value.
- **`az resource tag --tags <tag-name>=<tag-value>`**: Assign tags to a resource.

## Compute Commands

### Virtual Machines
- **`az vm create`**: Create a virtual machine.
- **`az vm deallocate`**: Deallocate a virtual machine to save costs.
- **`az vm list-ip-addresses`**: List public and private IP addresses of VMs.
- **`az vm image list`**: List available VM images.

### Containers and Kubernetes
- **`az container create`**: Create a new Azure container instance.
- **`az aks create`**: Set up a new Azure Kubernetes Service (AKS) cluster.
- **`az aks nodepool add`**: Add a node pool to an AKS cluster.

### Azure Batch
- **`az batch account create`**: Create an Azure Batch account.
- **`az batch pool create`**: Create a pool of compute nodes.
- **`az batch job create`**: Create a job to execute on a pool.

## Networking Commands

### Load Balancers
- **`az network lb create`**: Create a load balancer.
- **`az network lb rule create`**: Define load balancer rules.
- **`az network lb probe create`**: Set up a health probe for the load balancer.

### Virtual Network Peering
- **`az network vnet peering create`**: Establish VNet peering between two VNets.
- **`az network vnet peering list`**: List VNet peerings.

## Storage Commands

### Blob Storage
- **`az storage blob create`**: Create a blob in a storage account.
- **`az storage blob delete`**: Delete a blob.
- **`az storage blob snapshot`**: Create a snapshot of a blob.

### File Shares
- **`az storage file share create`**: Create a file share.
- **`az storage file list`**: List files in a file share.

### Azure Data Lake
- **`az dls account create`**: Create a Data Lake Store account.
- **`az dls filesystem create`**: Create a directory or file in Data Lake Store.

## Data and Analytics Commands

### Azure Synapse Analytics
- **`az synapse workspace create`**: Create a Synapse workspace.
- **`az synapse spark pool create`**: Set up a Spark pool.
- **`az synapse sql pool create`**: Create an SQL pool.

### Azure Data Factory
- **`az datafactory create`**: Create a Data Factory instance.
- **`az datafactory pipeline create`**: Set up a data pipeline.
- **`az datafactory pipeline run`**: Trigger a pipeline run.

## AI and Machine Learning Commands

### Azure Cognitive Services
- **`az cognitiveservices account create`**: Set up a Cognitive Services account.
- **`az cognitiveservices account keys list`**: Get access keys for the account.

### Azure Machine Learning
- **`az ml workspace create`**: Create a machine learning workspace.
- **`az ml compute create`**: Provision compute resources for ML.
- **`az ml model deploy`**: Deploy a model for inference.

## Automation Commands

### Azure Automation Accounts
- **`az automation account create`**: Create an Automation Account.
- **`az automation runbook create`**: Create a new runbook.
- **`az automation schedule create`**: Set up a schedule for a runbook.

### Azure Logic Apps
- **`az logic workflow create`**: Create a new logic app workflow.
- **`az logic workflow run trigger`**: Trigger a logic app run manually.

## DevOps and CI/CD Commands

### Azure DevOps Projects
- **`az devops project create`**: Create a DevOps project.
- **`az pipelines create`**: Set up a new pipeline.
- **`az boards work-item create`**: Create a work item in Azure Boards.

### Azure Repos
- **`az repos create`**: Create a repository.
- **`az repos delete`**: Delete a repository.
- **`az repos policy create`**: Set up policies for branch protection.

## Identity and Access Management

### Azure Active Directory (AAD)
- **`az ad user create`**: Create a new AAD user.
- **`az ad group create`**: Create an AAD group.
- **`az ad sp create-for-rbac`**: Generate a service principal for role-based access control.

### Role Assignments
- **`az role assignment create`**: Assign a role to a user, group, or service principal.
- **`az role assignment delete`**: Remove a role assignment.
- **`az role definition list`**: List all available roles.

### Managed Identities
- **`az identity create`**: Create a managed identity.
- **`az identity show`**: Display information about a managed identity.

## Security Commands

### Azure Security Center
- **`az security assessment create`**: Create a security assessment.
- **`az security contact create`**: Configure security contact details.

### Key Vault and Secrets Management
- **`az keyvault secret set`**: Set a secret in a key vault.
- **`az keyvault key create`**: Create a key in a key vault.

### Compliance Policies
- **`az policy definition create`**: Define a custom policy.
- **`az policy assignment create`**: Assign a policy to a resource scope.

## Advanced Monitoring and Troubleshooting

### Azure Monitor
- **`az monitor metrics list`**: List metrics for a resource.
- **`az monitor activity-log list`**: Retrieve the activity log for a resource.
- **`az monitor diagnostics setting create`**: Configure diagnostics settings.

### Log Analytics
- **`az monitor log-analytics workspace create`**: Set up a Log Analytics workspace.
- **`az monitor log-analytics query`**: Run a query in Log Analytics.

### Azure Resource Health
- **`az resource health metadata list`**: Retrieve metadata about resource health.
- **`az resource health events list`**: List health events for a resource.

## Cost Management and Optimization

### Azure Cost Management
- **`az costmanagement report create`**: Generate a cost report.
- **`az consumption usage list`**: List usage details for cost analysis.

### Advisor Recommendations
- **`az advisor recommendation list`**: Get Advisor recommendations.
- **`az advisor recommendation disable`**: Disable a recommendation.

## Miscellaneous Useful Commands

### CLI Configuration
- **`az configure`**: Configure Azure CLI settings.
- **`az feedback`**: Send feedback to Microsoft about the CLI.

### Container Registries
- **`az acr create`**: Create an Azure Container Registry.
- **`az acr repository list`**: List repositories in a container registry.

---

## Additional Tips
- **Scripting**: Combine CLI commands into scripts for automation.
- **Using `--help`**: Get details about any command with the `--help` flag.
- **Setting CLI Output Formats**: Set output to table, JSON, or YAML for easier viewing: `az configure --defaults output=<format>`.
- **Aliasing**: Create short command aliases for frequently used commands.

This expanded list provides more in-depth Azure CLI capabilities across various Azure services, catering to advanced management, automation, and monitoring tasks in the Azure cloud.

# Comprehensive Azure CLI Command Guide

## Core Services

### Resource Management and Governance
- **`az resource list`**: List all resources in a subscription.
- **`az policy state list`**: Check policy compliance state.
- **`az blueprint create`**: Create an Azure Blueprint to define repeatable sets of resources.

### Subscriptions and Billing
- **`az billing invoice list`**: List invoices for the subscription.
- **`az billing period list`**: Get details about billing periods.
- **`az consumption budget create`**: Create a budget to manage costs.

## Compute

### Virtual Machine Scale Sets
- **`az vmss create`**: Create a VM Scale Set (VMSS) for autoscaling.
- **`az vmss scale`**: Scale a VM Scale Set up or down.
- **`az vmss list-instances`**: List all instances in a VM Scale Set.

### Azure HPC (High Performance Computing)
- **`az hpc create`**: Set up an HPC environment.
- **`az hpc node create`**: Add compute nodes to HPC.
- **`az hpc job submit`**: Submit a job to run on HPC resources.

## Networking

### VPN Gateway
- **`az network vnet-gateway create`**: Set up a VPN gateway for secure communication.
- **`az network vpn-connection create`**: Establish a VPN connection between virtual networks.
- **`az network vpn-client generate`**: Generate a VPN client for end-users.

### ExpressRoute
- **`az network express-route create`**: Create an ExpressRoute connection for private connectivity.
- **`az network express-route peering create`**: Configure peering settings for ExpressRoute.
- **`az network express-route gateway create`**: Set up an ExpressRoute gateway.

## Storage

### Azure NetApp Files
- **`az netappfiles account create`**: Create an Azure NetApp Files account.
- **`az netappfiles pool create`**: Create a capacity pool in NetApp.
- **`az netappfiles volume create`**: Create a volume within the NetApp capacity pool.

### Azure Managed Disks
- **`az disk create`**: Create a managed disk.
- **`az disk snapshot create`**: Capture a snapshot of a managed disk.
- **`az disk encryption enable`**: Encrypt a managed disk.

## Data Services

### Cosmos DB
- **`az cosmosdb create`**: Create a Cosmos DB account.
- **`az cosmosdb database create`**: Create a database in Cosmos DB.
- **`az cosmosdb collection create`**: Create a collection within a Cosmos DB database.

### Azure Databricks
- **`az databricks workspace create`**: Create a Databricks workspace.
- **`az databricks cluster create`**: Create a cluster within the workspace.
- **`az databricks job run-now`**: Trigger a Databricks job immediately.

### Azure SQL Managed Instance
- **`az sql mi create`**: Create a SQL Managed Instance.
- **`az sql mi failover`**: Trigger a failover for high availability.
- **`az sql mi tde-key set`**: Set a Transparent Data Encryption (TDE) key.

## AI, ML, and Analytics

### Azure Stream Analytics
- **`az stream-analytics job create`**: Set up a Stream Analytics job.
- **`az stream-analytics output create`**: Configure an output for data processed by Stream Analytics.
- **`az stream-analytics input create`**: Define an input source for Stream Analytics.

### Azure Cognitive Search
- **`az search service create`**: Create an Azure Cognitive Search service.
- **`az search index create`**: Define a search index.
- **`az search indexer create`**: Set up an indexer to pull data into the search index.

### Machine Learning Workflows
- **`az ml experiment create`**: Create an ML experiment.
- **`az ml pipeline create`**: Build an ML pipeline for batch processing.
- **`az ml endpoint create`**: Set up an endpoint for model deployment.

## Serverless Computing

### Azure Functions
- **`az functionapp create`**: Deploy a function app for serverless computing.
- **`az functionapp function create`**: Add a function to a function app.
- **`az functionapp deployment source config`**: Configure a deployment source (e.g., GitHub) for CI/CD.

### Azure Logic Apps Advanced
- **`az logic workflow trigger-history list`**: View the run history of a workflow.
- **`az logic workflow show`**: Display details about a specific workflow.
- **`az logic app restart`**: Restart a Logic App in case of errors.

## Hybrid and Multi-cloud

### Azure Arc
- **`az connectedk8s connect`**: Connect a Kubernetes cluster to Azure Arc.
- **`az connectedmachine connect`**: Connect a non-Azure VM to Azure Arc.
- **`az arcappliance create`**: Deploy an Arc appliance for hybrid and multi-cloud governance.

## Security and Identity

### Azure Sentinel
- **`az sentinel workspace create`**: Create a Sentinel workspace.
- **`az sentinel alert-rule create`**: Set up an alert rule in Sentinel.
- **`az sentinel incident list`**: Retrieve a list of security incidents.

### Identity Protection
- **`az identity protection risk-detection list`**: List risky sign-ins.
- **`az identity protection user-risk-policy create`**: Define a policy for risky user behavior.
- **`az identity protection user-risk update`**: Update user risk status.

### Conditional Access
- **`az ad conditional-access policy create`**: Create a conditional access policy.
- **`az ad conditional-access policy list`**: List all conditional access policies.

## Governance

### Azure Policy and Compliance
- **`az policy assignment identity assign`**: Assign a managed identity to a policy assignment.
- **`az blueprint artifact create`**: Add artifacts (e.g., policies, roles) to a blueprint.
- **`az policy remediation create`**: Initiate remediation tasks for non-compliant resources.

### Azure Cost Management Advanced
- **`az costmanagement export create`**: Set up a recurring cost export to storage.
- **`az consumption budget show`**: Retrieve budget details and remaining limits.
- **`az consumption forecast show`**: View forecasted usage and cost predictions.

## Migration and Backup

### Azure Migrate
- **`az migrate project create`**: Create an Azure Migrate project.
- **`az migrate assessment create`**: Perform an assessment for migration readiness.
- **`az migrate discovery start`**: Start the discovery process for servers.

### Azure Site Recovery
- **`az recovery-services vault create`**: Set up a recovery vault.
- **`az recoveryservices protection enable-for-vm`**: Enable backup for a VM.
- **`az recoveryservices vault backup-job show`**: Display backup job details.

## Advanced Monitoring

### Azure Application Insights
- **`az monitor app-insights component create`**: Create an Application Insights resource.
- **`az monitor app-insights query`**: Run a query in Application Insights.
- **`az monitor app-insights analytics-item show`**: Show details about analytics items (e.g., workbooks, alerts).

### Traffic Manager
- **`az network traffic-manager profile create`**: Set up a Traffic Manager profile for DNS-based load balancing.
- **`az network traffic-manager endpoint create`**: Define endpoints for Traffic Manager.
- **`az network traffic-manager profile update`**: Update configuration for a Traffic Manager profile.

## Developer Tools

### Azure Blockchain Service
- **`az blockchain member create`**: Create a blockchain member in an Azure Blockchain Service.
- **`az blockchain transaction-node create`**: Create a transaction node in the blockchain network.
- **`az blockchain data-manager create`**: Set up data management within a blockchain member.

### Azure API Management
- **`az apim create`**: Create an API Management instance.
- **`az apim api create`**: Add a new API to the API Management service.
- **`az apim policy create`**: Define policies (e.g., rate limiting) for API Management.

## Optimization

### Azure Advisor Automation
- **`az advisor configuration update`**: Configure Advisor settings for recommendations.
- **`az advisor recommendation refresh`**: Manually refresh Advisor recommendations.

---

### Additional Tips
- **Automation with PowerShell**: Combine Azure CLI with PowerShell for more complex automation tasks.
- **Backup and Export Data**: Use `az storage` commands to back up Azure CLI configurations and logs.
- **Interactive Mode**: Use `az interactive` for a guided, command-line Azure experience with autocomplete.
- **Batch Processing**: Use CLI commands with loops and conditionals in scripts for processing multiple resources simultaneously.

This advanced collection covers comprehensive Azure CLI commands across data management, security, migration, developer tools, serverless computing, hybrid environments, and monitoring. It’s designed for a thorough Azure management experience tailored to meet both basic and high-level operational needs.

