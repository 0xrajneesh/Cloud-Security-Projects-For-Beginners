# Monitoring and Logging in Azure with Azure Security Center

## Introduction

In this project, you'll learn how to monitor and log activities in Azure using Azure Security Center. Azure Security Center provides advanced threat protection across your hybrid cloud workloads. We'll cover setting up Security Center, configuring security policies, and monitoring and responding to security alerts.

## Pre-requisites

- Basic understanding of cloud computing
- An Azure account (free trial available)
- Basic knowledge of command-line interface (CLI)

## Lab Set-up and Tools

1. **Azure Account**: Sign up for a free Azure account if you don't have one.
2. **Azure Portal**: Access to the Azure Management Portal.
3. **Azure CLI**: Install the Azure Command Line Interface (CLI) on your local machine.

## Exercises

### Exercise 1: Enable Azure Security Center

#### Steps

1. Log in to the [Azure Portal](https://portal.azure.com/).
2. Navigate to "Security Center".
3. Click on "Get started".
4. Select the subscription you want to protect.
5. Enable the "Standard" tier for full Security Center capabilities.
6. Click "Upgrade" to enable Azure Security Center.

#### Expected Output

- Azure Security Center enabled and configured for your subscription.

### Exercise 2: Configure Security Policies

#### Steps

1. In the Azure Portal, navigate to "Security Center".
2. Click on "Security policy".
3. Select your subscription.
4. Configure the policy settings (e.g., enable recommendations for virtual machines, app services, SQL databases).
5. Click "Save".

#### Expected Output

- Security policies configured to provide recommendations for various Azure resources.

### Exercise 3: Enable Diagnostic Logs

#### Steps

1. Navigate to a resource group in the Azure Portal.
2. Select a resource (e.g., a virtual machine).
3. Click on "Diagnostic settings" under the "Monitoring" section.
4. Click on "Add diagnostic setting".
5. Configure the settings:
    - Name: `myDiagnosticSetting`
    - Log: Select all relevant logs (e.g., Audit, Security)
    - Destination: Send to Log Analytics workspace
6. Click "Save".

#### Expected Output

- Diagnostic logs enabled for the selected resource and sent to Log Analytics.

### Exercise 4: Set Up Log Analytics Workspace

#### Steps

1. In the Azure Portal, navigate to "Log Analytics workspaces".
2. Click on "Create".
3. Configure the workspace settings:
    - Name: `myLogAnalyticsWorkspace`
    - Resource group: Select an existing or create a new one
    - Location: Select a region
4. Click "Review + create" and then "Create".
5. Navigate back to your resource's "Diagnostic settings" and link to the newly created Log Analytics workspace.

#### Expected Output

- Log Analytics workspace `myLogAnalyticsWorkspace` created and linked to the diagnostic settings.

### Exercise 5: Monitor Security Alerts and Recommendations

#### Steps

1. Navigate to "Security Center" in the Azure Portal.
2. Click on "Security alerts" to view any active alerts.
3. Investigate any listed alerts by clicking on them to view details and suggested actions.
4. Click on "Recommendations" to view security recommendations for your resources.
5. Implement suggested actions to improve your security posture.

#### Expected Output

- Active security alerts and recommendations reviewed and appropriate actions taken.

## Conclusion

By completing these exercises, you have successfully enabled Azure Security Center, configured security policies, enabled diagnostic logs, set up a Log Analytics workspace, and monitored security alerts and recommendations. These steps are essential for maintaining the security and compliance of your Azure environment.
