## Azure Monitor Agent Migration for Log Analytics Agent Users

**Introduction**

This repository provides resources and instructions to migrate from the deprecated Log Analytics agent to the Azure Monitor agent for collecting data from your VMs and on-premises servers (Ubuntu/Linux and Windows).

**Important Dates**

* **End of support for Log Analytics agent:** August 31, 2024

**Benefits of Migration**

* Continued data collection for your Azure Monitor workspace.
* Access to improved functionalities of the Azure Monitor agent.

## Preparation

Before you begin the migration process, take some time to prepare:

1. **Review Resources:** Familiarize yourself with the official Microsoft migration guide: https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-migration
2. **Identify Workspaces:** Locate the Azure Log Analytics workspace(s) currently associated with your Log Analytics agents. You can find this information within the Azure portal under **Monitor > Log Analytics workspaces**.

## Migration Steps

**1. Install Azure Monitor Agent**

The installation process differs slightly depending on your environment:

* **VMs (Azure and Azure Arc-enabled On-Premises):**

    ```
    1. Login to the Azure portal and navigate to your VM or Azure Arc-enabled server.
    2. Go to Settings > Extensions.
    3. Click on Add and search for "Azure Monitor Agent for VMs".
    4. Select the appropriate version and configure the workspace ID associated with your Azure Monitor workspace.
    5. Deploy the extension to your VM.
    ```

* **On-Premises VMs (No Azure Arc):**

    ```
    1. Download the installer for your specific operating system (Windows or Linux) from the following links:
        * Windows: [https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-windows-client](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-windows-client)
        * Linux: [https://learn.microsoft.com/en-us/azure/azure-monitor/agents/agent-linux](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/agent-linux)
    2. Follow the installation instructions provided on the respective download pages. Remember to specify the workspace ID during installation.
    ```

**2. Data Collection Rule Creation**

Data Collection Rules (DCRs) define what data is collected by the Azure Monitor agent. You can generate these rules based on your existing Log Analytics agent configuration:

    1. Access the DCR Config Generator tool from the Azure portal by navigating to **Monitor > Log Analytics workspaces > [Your Workspace] > Agents > Azure Monitor Agent**.
    2. Click on **Data collection rules** and select **Generate data collection rules**.
    3. Follow the on-screen instructions to connect to your workspace and download the generated DCRs.

**3. Define Data Collection**

The generated DCRs (JSON files) define the initial data collection configuration. Review and customize these files to specify the specific data you want to collect from each agent (e.g., performance counters, logs).

**4. Testing and Deployment (Future Update)**

A dedicated section for Testing and Deployment will be added in a future update. This section will detail steps for testing the migration on non-production VMs, optionally disabling data collection from Log Analytics agents during testing, and finally deploying the Azure Monitor agent with data collection rules to your production VMs.

**5. Full Deployment and Cleanup (Future Update)**

A dedicated section for Full Deployment and Cleanup will be added in a future update. This section will provide steps for deploying the DCRs and associating them with all production VMs/servers. You will also learn about the option to uninstall the Log Analytics agent after successful migration.

## Additional Resources

* https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-windows-client
* https://learn.microsoft.com/en-us/azure/azure-monitor/agents/agent-linux
* https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-migration#migration-guidance
* https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-migration-tools#using-ama-migration-helper

## Disclaimer

The information provided in this repository is for educational purposes only. Refer to official Microsoft documentation for the latest updates and detailed instructions.
