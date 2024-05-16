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


---

### File Integrity Monitoring (FIM)


File Integrity Monitoring (FIM) examines operating system files, Windows registries, application software, and Linux system files for changes that might indicate an attack.

FIM (file integrity monitoring) uses the Azure Change Tracking solution to track and identify changes in your environment. When FIM is enabled, you have a Change Tracking resource of type Solution. If you remove the Change Tracking resource, you'll also disable the File Integrity Monitoring feature in Defender for Cloud. FIM lets you take advantage of Change Tracking directly in Defender for Cloud. For data collection frequency details, see Change tracking data collection details.

Defender for Cloud recommends entities to monitor with FIM, and you can also define your own FIM policies or entities to monitor. FIM informs you about suspicious activity such as:

- File and registry key creation or removal
- File modifications (changes in file size, access control lists, and hash of the content)
- Registry modifications (changes in size, access control lists, type, and content)

Many regulatory compliance standards require implementing FIM controls, such as PCI-DSS and ISO 17799.

To provide File Integrity Monitoring (FIM), the Azure Monitor Agent (AMA) collects data from machines according to data collection rules. When the current state of your system files is compared with the state during the previous scan, FIM notifies you about suspicious modifications.

File Integrity Monitoring with the Azure Monitor Agent offers:

- Compatibility with the unified monitoring agent - Compatible with the Azure Monitor Agent that enhances security, reliability, and facilitates multi-homing experience to store data.
- Compatibility with tracking tool- Compatible with the Change tracking (CT) extension deployed through the Azure Policy on the client's virtual machine. You can switch to Azure Monitor Agent (AMA), and then the CT extension pushes the software, files, and registry to AMA.
- Simplified onboarding- You can onboard FIM from Microsoft Defender for Cloud.
- Multi-homing experience – Provides standardization of management from one central workspace. You can transition from Log Analytics (LA) to AMA so that all VMs point to a single workspace for data collection and maintenance.
- Rules management – Uses Data Collection Rules to configure or customize various aspects of data collection. For example, you can change the frequency of file collection.




### Reference

- (https://azure.microsoft.com/en-in/pricing/details/defender-for-cloud/)
- (https://learn.microsoft.com/en-us/azure/defender-for-cloud/file-integrity-monitoring-enable-ama)
- (https://learn.microsoft.com/en-us/azure/defender-for-cloud/file-integrity-monitoring-overview)
- (https://learn.microsoft.com/en-us/azure/network-watcher/connection-monitor-connected-machine-agent?tabs=WindowsScript)
- (https://learn.microsoft.com/en-us/azure/azure-arc/servers/agent-overview)
- (https://learn.microsoft.com/en-us/defender-cloud-apps/get-started)
- (https://learn.microsoft.com/en-us/azure/defender-for-cloud/quickstart-onboard-machines#connect-on-premises-machines-by-using-the-azure-portal)
