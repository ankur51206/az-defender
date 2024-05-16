# Setting Up Microsoft Defender for On-Premises Servers Connected to Azure

This guide provides detailed steps to set up Microsoft Defender for your on-premises servers that are connected to Azure using Azure Arc. Follow these instructions to ensure your servers are properly protected.

## Prerequisites
- Ensure your on-premises servers are connected to Azure via VPN or ExpressRoute.
- Azure subscription with Microsoft Defender for Cloud enabled.
- Azure Arc enabled on your Azure subscription.

## Steps to Set Up Microsoft Defender

### 1. Ensure Connectivity

Ensure your on-premises servers are connected to Azure through a VPN or ExpressRoute.

### 2. Install the Azure Arc Agent

#### For Windows Servers
1. **Download and Install the Agent**
   - Download the Azure Connected Machine agent from the Azure portal.
   - Run the installer on the server.
   ```shell
   azcmagent connect --resource-group <ResourceGroupName> --tenant-id <TenantID> --subscription-id <SubscriptionID>

    Install the Connected Machine agent on a Windows machine

For Linux Servers

    Download and Install the Agent
        Use the following script to install the agent:

curl -sSL https://aka.ms/azcmagent | sudo bash

    Connect the agent to Azure Arc:

    sudo azcmagent connect --resource-group <ResourceGroupName> --tenant-id <TenantID> --subscription-id <SubscriptionID>

        Install the Connected Machine agent on a Linux machine

3. Enable Microsoft Defender for Cloud

    Navigate to Defender for Cloud in Azure Portal
        Go to the Azure portal.
        Navigate to "Microsoft Defender for Cloud."
        Enable it if not already enabled.
        Get started with Microsoft Defender for Cloud

4. Add On-Premises Servers to Microsoft Defender for Cloud

    Register the Servers with Defender for Cloud
        Ensure that the Azure Arc-enabled servers are visible in the Azure portal.
        In the Defender for Cloud dashboard, navigate to “Inventory” and verify that the Arc-enabled servers are listed.
        Enable Defender for Servers on these resources.
        Deploy Microsoft Defender for Cloud on hybrid and multi-cloud environments

5. Configure Microsoft Defender Plans

    Select and Configure Plans
        Navigate to “Environment settings” in Defender for Cloud.
        Select your subscription and click on “Defender plans.”
        Enable the Defender plans that are appropriate for your workloads.
        Microsoft Defender for Cloud pricing

6. Install Microsoft Defender for Endpoint

For Windows Servers

    Onboard the Server
        Use the provided script in the Microsoft 365 Defender portal to onboard your Windows server.
        Follow the detailed steps in the onboarding wizard.
        Onboard Windows servers to the Microsoft Defender for Endpoint service

For Linux Servers

    Install and Configure the Agent
        Follow the steps to install the Defender for Endpoint agent on your Linux servers.

    wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
    sudo dpkg -i packages-microsoft-prod.deb
    sudo apt-get update
    sudo apt-get install mdatp

        Configure the agent with your settings.
        Onboard Linux servers to the Microsoft Defender for Endpoint service

7. Configure Security Policies

    Create and Manage Policies
        Navigate to “Policy” in the Azure portal.
        Create new policies or use built-in policies to enforce compliance on your resources.
        Create and manage policies to enforce compliance

    Review Security Recommendations
        In Defender for Cloud, review the security recommendations for your Arc-enabled servers.
        Apply the recommended configurations to improve your security posture.
        Azure Security Center security policies



Connect On-Premises Machines Using the Azure Portal

Prerequisites

    An Azure subscription with Microsoft Defender for Cloud enabled.
    An existing Log Analytics workspace.

Steps to Onboard Windows Servers

    Sign in to the Azure portal:
        Go to Azure portal.

    Access Microsoft Defender for Cloud:
        In the Azure portal, search for "Microsoft Defender for Cloud" and select it.

    Configure Non-Azure Servers:
        In the Microsoft Defender for Cloud dashboard, select Getting started.
        Under Add non-Azure servers, click on Configure.

    Select or Create a Log Analytics Workspace:
        You will be prompted to select an existing Log Analytics workspace or create a new one if you don't have any.
        After selecting or creating the workspace, click OK.

    Download and Install the Windows Agent:
        A link to download the Windows Agent will be provided. Click the link to download.
        Run the installer on your target machine.
        During the installation, you will be prompted to enter the Workspace ID and Primary Key. These can be found in the Log Analytics workspace settings in the Azure portal.

    Configure the Agent:
        Follow the prompts in the installation wizard to complete the setup.
        Ensure the machine has internet connectivity to communicate with Azure.

    Verify Connection:
        Go back to the Azure portal, navigate to Microsoft Defender for Cloud > Inventory.
        Verify that your server appears in the list with a healthy status.

Steps to Onboard Linux Servers

    Sign in to the Azure portal:
        Go to Azure portal.

    Access Microsoft Defender for Cloud:
        In the Azure portal, search for "Microsoft Defender for Cloud" and select it.

    Configure Non-Azure Servers:
        In the Microsoft Defender for Cloud dashboard, select Getting started.
        Under Add non-Azure servers, click on Configure.

    Select or Create a Log Analytics Workspace:
        You will be prompted to select an existing Log Analytics workspace or create a new one if you don't have any.
        After selecting or creating the workspace, click OK.

    Download and Install the Linux Agent:
        A wget command will be provided. Copy this command.
        On your Linux machine, open a terminal and run the copied wget command to download and install the agent.

    Run the Installation Command:
        Execute the wget command in the terminal. This will download the necessary installation files and begin the installation process.
        Follow the on-screen instructions to complete the installation.

    Verify Connection:
        Validate that the Operations Management Suite Agent is installed by running pgrep omsagent. This command should return the omsagent process ID.
        The logs for the agent can be found at /var/opt/microsoft/omsagent/<workspace id>/log/.

    Confirm in Azure Portal:
        Go back to the Azure portal, navigate to Microsoft Defender for Cloud > Inventory.
        Verify that your Linux server appears in the list.

For detailed instructions and troubleshooting, refer to the Microsoft documentation.





References

    https://learn.microsoft.com/en-us/azure/azure-arc/servers/agent-overview
    https://learn.microsoft.com/en-us/azure/azure-arc/servers/onboard-portal
    https://learn.microsoft.com/en-us/azure/defender-for-cloud/tutorial-enable-servers-plan
    https://azure.microsoft.com/en-us/pricing/details/defender-for-cloud/
    https://learn.microsoft.com/en-us/azure/azure-arc/servers/learn/quick-enable-hybrid-vm
    
    
