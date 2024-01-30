Welcome to the **Coolify Workflows for Automated n8n Backup & Update**! This innovative n8n template is meticulously crafted to automate the backup and update process of your n8n instance, seamlessly integrating with Coolify V4 for Docker management. With this workflow, you can ensure your n8n instance remains updated with the latest features and improvements while keeping your valuable credentials and workflows safely backed up.

![cover](https://live.staticflickr.com/65535/53496632070_428c073f14_o.png)

## 🚀 Features Overview

- **Automated Schedule**: Utilizes a `Schedule Trigger` node to regularly check for new n8n versions, ensuring your instance is always up-to-date.
- **Backup and Security**: Automatically exports all credentials and workflows, ensuring your data is safe before proceeding with any updates.
- **Telegram Notifications**: Sends real-time notifications through Telegram, keeping you informed about the backup status and update details.
- **Coolify Integration**: Leverages Coolify for Docker management, facilitating smooth updates and deployment of n8n instances with minimal downtime.

## 🎥 Workflow Demonstration

Explore the workflow in action and understand its functionality with this detailed video guide:
[![Watch the Workflow Video](https://community.n8n.io/uploads/default/original/3X/f/d/fdef5b1501cbb08d61f848d24550b5fab500e16b.png)](https://youtu.be/Zc1rxQJGgKo)

This guide will walk you through the workflow, from configuration to execution, ensuring you can leverage its full potential.

## 📋 Step-by-Step Guide

### 1. **Scheduled Trigger**
Initiates the workflow at predetermined intervals to check for n8n updates.

### 2. **Check for Updates**
Determines if there's a new version of n8n available by comparing the current version against the latest release.

### 3. **Backup Credentials & Workflows**
Exports all credentials and workflows, ensuring your configurations are preserved before any updates.

### 4. **Real-Time Telegram Notifications**
Keeps you informed with detailed Telegram messages regarding updates, backup statuses, and successful update completion.

### 5. **Update Execution**
Automatically applies the update using Coolify's Docker management capabilities if a new version is detected, ensuring a smooth transition with minimal service interruption.

## ⚙ Configuration Essentials

Before using the workflow, ensure the following settings are configured:

| Requirement | Description | Source |
| ---- | ---- | ---- |
| Working Method (CLI choose 1 - HTTP choose 2) | Method of checking the current n8n version: CLI or HTTP. | Choose based on your n8n instance setup. |
| N8N Instance (domain or IP:PORT) | Domain or IP address and port of your n8n instance. | Only required if you choose the HTTP method. |
| Telegram Chat ID | Identifier for receiving Telegram alerts. | Your Telegram account settings. |
| Coolify Webhook URL | URL to trigger Coolify deployments. | `Coolify Dashboard > Your Project > Webhooks` |
| Coolify API Token | Access token for Coolify API integrations. | `Coolify Dashboard > Security > API Tokens` |

> **Tip**: Refer to the [Coolify Documentation](https://coolify.io/docs/api/authentication) for comprehensive setup instructions. Ensure accurate configuration for seamless workflow operation.

## 🌟 Conclusion

This workflow is designed to streamline the maintenance of your n8n instance, automating updates and backups with precision. It ensures your system is not only up-to-date but also securely backed up, allowing you to focus more on building and optimizing your n8n workflows.

If you encounter any issues or have suggestions for improvement, feel free to engage with the community on the [n8n community forum](https://community.n8n.io). Your feedback is invaluable in enhancing this workflow further.

Keep your n8n instance optimized and secure with the [Coolify](https://coolify.io) Workflows for Automated n8n Backup & Update.