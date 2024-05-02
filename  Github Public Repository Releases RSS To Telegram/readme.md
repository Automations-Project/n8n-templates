![Static Badge](https://img.shields.io/badge/Template%20Version-V0.05-pink), ![Static Badge](https://img.shields.io/badge/Node-RssFeedReadTrigger-080808),![Static Badge](https://img.shields.io/badge/Node-Markdown-080808),![Static Badge](https://img.shields.io/badge/Node-Code-080808),![Static Badge](https://img.shields.io/badge/Node-SplitInBatches-080808),![Static Badge](https://img.shields.io/badge/Node-HttpRequest-080808),![Static Badge](https://img.shields.io/badge/Node-NoOp-080808)
![Static Badge](https://github.com/Automations-Project/n8n-templates/blob/main/%20Github%20Public%20Repository%20Releases%20RSS%20To%20Telegram/idd6TtF-kc.png)
#  Github Public Repository Releases RSS To Telegram

[![Screenshot of template Github Public Repository Releases RSS To Telegram](https://img.youtube.com/vi_webp/IAlFNNILi4A/maxresdefault.webp)](https://youtu.be/IAlFNNILi4A)

#### Overview

The **[n8n] Github Public Repository Releases RSS To Telegram** workflow is designed to automate the distribution of new release updates from GitHub repositories directly to Telegram channels or users. This workflow monitors a specified GitHub repository for new releases and automatically sends formatted messages to a designated Telegram channel or user account, ensuring subscribers stay updated on the latest developments.

#### Key Use Cases and Benefits

* **Developer Updates**: Keep your development team or user community informed about new releases or updates.
* **Automated Notifications**: Eliminate the need for manual monitoring and updating, saving time and ensuring timely notifications.
* **Customizable Messaging**: Tailor the notification messages to include specific details or promotional content relevant to your audience.

#### Services/APIs Utilized

* **GitHub**: Monitors public repository releases through the RSS feed.
* **Telegram**: Sends automated messages to specified channels or users.

#### Configuration Instructions

1. **RSS Feed Trigger**: Replace the placeholder URL `https://github.com/(Username Here)/(Repo Here)/releases.atom` with the URL of your GitHub repository's release RSS feed.
2. **Config Node**: Enter your Telegram bot token and the ID of the channel or user account where notifications will be sent.
3. **Final Node**: Customize the message template as needed to include any additional information or promotional content.

#### Screenshot

![Screenshot of template Github Public Repository Releases RSS To Telegram](https://live.staticflickr.com/65535/53647284529_8043c5205e_o.png)

#### Additional Notes

* Ensure your Telegram bot has the necessary permissions to post in the designated channel or chat.
* Test the workflow with a dummy release to verify that notifications are sent as expected.

#### Support and Contributions

For support, questions, or contributions, please visit the [n8n community forum](https://community.n8n.io/) or the GitHub repository hosting this workflow. We welcome your feedback and contributions to improve this template.
