Steps to Set Up Microsoft Defender using Azure Arc
1. Ensure Connectivity

Ensure your on-premises servers are connected to Azure through a VPN or ExpressRoute.
2. Install the Azure Arc Agent
For Windows Servers

    Download and Install the Agent:
        Download the Azure Connected Machine agent from the Azure portal.
        Run the installer on the server.

    Connect the Agent to Azure Arc:


    azcmagent connect --resource-group <ResourceGroupName> --tenant-id <TenantID> --subscription-id <SubscriptionID>

For Linux Servers

    Download and Install the Agent:


curl -sSL https://aka.ms/azcmagent | sudo bash

Connect the Agent to Azure Arc:


    sudo azcmagent connect --resource-group <ResourceGroupName> --tenant-id <TenantID> --subscription-id <SubscriptionID>

3. Enable Microsoft Defender for Cloud

    Navigate to Defender for Cloud in Azure Portal.
    Go to "Microsoft Defender for Cloud" and enable it if not already enabled.

4. Add On-Premises Servers to Microsoft Defender for Cloud

    Register the Servers with Defender for Cloud.
    Ensure that the Azure Arc-enabled servers are visible in the Azure portal.
    Enable Defender for Servers on these resources.

5. Configure Microsoft Defender Plans

    Navigate to “Environment settings” in Defender for Cloud.
    Select your subscription and enable the appropriate Defender plans.

6. Install Microsoft Defender for Endpoint
For Windows Servers

    Onboard the Server using the provided script in the Microsoft 365 Defender portal.
    Follow the detailed steps in the onboarding wizard.

For Linux Servers

    Follow the steps to install the Defender for Endpoint agent on your Linux servers.
    Configure the agent with your settings.

7. Configure Security Policies

    Create and Manage Policies in the Azure portal to enforce compliance on your resources.

8. Review Security Recommendations

    In Defender for Cloud, review the security recommendations for your Arc-enabled servers.
    Apply the recommended configurations to improve your security posture.




Steps to Connect On-Premises Machines Using the Azure Portal
Prerequisites

    An Azure subscription with Microsoft Defender for Cloud enabled.
    An existing Log Analytics workspace.

Onboarding Windows Servers

    Sign in to the Azure portal:
        Go to Azure portal.

    Access Microsoft Defender for Cloud:
        In the Azure portal, search for "Microsoft Defender for Cloud" and select it.

    Configure Non-Azure Servers:
        In the Microsoft Defender for Cloud dashboard, select Getting started.
        Under Add non-Azure servers, click on Configure.

    Select or Create a Log Analytics Workspace:
        Select an existing Log Analytics workspace or create a new one.
        Click OK after selecting or creating the workspace.

    Download and Install the Windows Agent:
        Download the Windows Agent from the provided link.
        Run the installer on your target machine.
        Enter the Workspace ID and Primary Key during installation.

    Verify Connection:
        Go back to the Azure portal and navigate to Microsoft Defender for Cloud > Inventory.
        Verify that your server appears in the list with a healthy status.

Onboarding Linux Servers

    Sign in to the Azure portal:
        Go to Azure portal.

    Access Microsoft Defender for Cloud:
        In the Azure portal, search for "Microsoft Defender for Cloud" and select it.

    Configure Non-Azure Servers:
        In the Microsoft Defender for Cloud dashboard, select Getting started.
        Under Add non-Azure servers, click on Configure.

    Select or Create a Log Analytics Workspace:
        Select an existing Log Analytics workspace or create a new one.
        Click OK after selecting or creating the workspace.

    Download and Install the Linux Agent:
        Copy the provided wget command.
        Run the command in the terminal of your Linux machine.

    Verify Connection:
        Validate that the Operations Management Suite Agent is installed.
        Check that your Linux server appears in Microsoft Defender for Cloud > Inventory.
