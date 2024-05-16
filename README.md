### Setting Up Microsoft Defender with Azure Arc

#### 1. Ensure Connectivity

Ensure on-premises servers are connected to Azure through VPN or ExpressRoute.

#### 2. Install Azure Arc Agent

##### For Windows Servers

- Download and Install Agent:
  - Download Azure Connected Machine agent from Azure portal.
  - Run installer on the server.

- Connect Agent to Azure Arc:
azcmagent connect --resource-group <ResourceGroupName> --tenant-id <TenantID> --subscription-id <SubscriptionID>

##### For Linux Servers

- Download and Install Agent:
curl -sSL https://aka.ms/azcmagent | sudo bash

- Connect Agent to Azure Arc:
sudo azcmagent connect --resource-group <ResourceGroupName> --tenant-id <TenantID> --subscription-id <SubscriptionID>


#### 3. Enable Microsoft Defender for Cloud

- Navigate to Defender for Cloud in Azure Portal.
- Go to "Microsoft Defender for Cloud" and enable if not already enabled.

#### 4. Add On-Premises Servers to Defender for Cloud

- Register servers with Defender for Cloud.
- Ensure Azure Arc-enabled servers are visible in Azure portal.
- Enable Defender for Servers on these resources.

#### 5. Configure Microsoft Defender Plans

- Navigate to “Environment settings” in Defender for Cloud.
- Select your subscription and enable appropriate Defender plans.

#### 6. Install Microsoft Defender for Endpoint

##### For Windows Servers

- Onboard Server using script in Microsoft 365 Defender portal.
- Follow steps in onboarding wizard.

##### For Linux Servers

- Install Defender for Endpoint agent on Linux servers.
- Configure agent with settings.

#### 7. Configure Security Policies

- Create and Manage Policies in Azure portal to enforce compliance.

#### 8. Review Security Recommendations

- In Defender for Cloud, review security recommendations for Arc-enabled servers.
- Apply recommended configurations to improve security posture.

---

### Connecting On-Premises Machines Using Azure Portal

#### Prerequisites

- Azure subscription with Microsoft Defender for Cloud enabled.
- Existing Log Analytics workspace.

#### Onboarding Windows Servers

- Sign in to Azure portal.
- Access Microsoft Defender for Cloud.
- Configure Non-Azure Servers.
- Select or Create a Log Analytics Workspace.
- Download and Install Windows Agent.
- Verify Connection.

#### Onboarding Linux Servers

- Sign in to Azure portal.
- Access Microsoft Defender for Cloud.
- Configure Non-Azure Servers.
- Select or Create a Log Analytics Workspace.
- Download and Install Linux Agent.
- Verify Connection.


[1] https://azure.microsoft.com/en-in/pricing/details/defender-for-cloud/
[2] https://learn.microsoft.com/en-us/azure/network-watcher/connection-monitor-connected-machine-agent?tabs=WindowsScript
[3] https://learn.microsoft.com/en-us/azure/azure-arc/servers/agent-overview
[4] https://learn.microsoft.com/en-us/defender-cloud-apps/get-started
[5] https://learn.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-machines#connect-on-premises-machines-by-using-the-azure-portal
