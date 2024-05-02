**Workflow Summary:**
**Additional Processing:**
- **Sticky Note** (n8n-nodes-base.stickyNote)
  Details:
    - **Content**:
```plaintext
## Readme
Usage:
- Update the `Rss Feed Trigger` with your own Github Repository `ID` and `Repo`.
 `https://github.com/(Username Here)/(Repo Here)/releases.atom`
- Update the `Config Node` with your own `Telegram Bot Token` & `Channel` or `Account` ID.
- Update the Message in `Final Node` As it contain promotional information regarding the repository used which is n8n in this usecase.







[![N8N Creator Profile - Nskha](https://cdn.statically.io/gh/Automations-Project/n8n-templates/main/stats.min.svg)](https://n8n.io/creators/nskha)
``` 
- **RSS Feed Trigger** (n8n-nodes-base.rssFeedReadTrigger)
  Details:
    - **Notes**: ```plaintext
Edit with your GitHub URL.``` 

**Error Handling:**
- **If not empty** (n8n-nodes-base.if)
- **If it was published after** (n8n-nodes-base.if)
**Additional Processing:**
- **Config** (n8n-nodes-base.set)
  Details:
    - ##### **telegram bot token**:
```javascript
7185874279:AAFnw5Ngzl8GOLBnBB5WedbEaBMBr9HGxt4
```
    - ##### **Telegram Channel / User ID**:
```javascript
346637642
```
    - **Notes**: ```plaintext
🤖 Enter Chat ID & Bot Token``` 
- **Convert HTML Rss to Markdown** (n8n-nodes-base.markdown)
  Details:
    - **Notes**: ```plaintext
📝From HTML to Markdown``` 
- **Clean & split the content for telegram limits. ** (n8n-nodes-base.code)
  Details:
    - **Notes**: ```plaintext
💦 if texts +2K characters``` 
- **Loop posting the content based on size** (n8n-nodes-base.splitInBatches)
  Details:
    - **Notes**: ```plaintext
🤖 loop posting the updates``` 

**Data Fetching and Processing:**
- **Telegram Loop Message Parts** (n8n-nodes-base.httpRequest)
**Additional Processing:**
- **Save Message ID for Reply** (n8n-nodes-base.set)
  Details:
    - ##### **result.message_id**:
```javascript
={{ $json.result.message_id }}
```
- **No Operation, do nothing** (n8n-nodes-base.noOp)
