# 📧 Send Emails from Obsidian

An n8n workflow that lets you send emails directly from your Obsidian notes — including attachments — using a simple Webhook trigger.

---

## ✨ Features

- Send emails directly from any Obsidian note
- Supports attachments (images, files) via base64 encoding
- Uses YAML frontmatter to define recipients, subject, CC, BCC, and more
- Automatically responds back to Obsidian after the email is sent
- Built-in test mode to verify your setup without sending real emails

---

## 🛠️ Requirements

- [n8n](https://n8n.io) (self-hosted or cloud)
- [Obsidian](https://obsidian.md) with the [Post Webhook plugin](https://github.com/Masterb1234/obsidian-post-webhook/)
- A connected Gmail account in n8n

---

## ⚙️ Setup

1. Import `workflow.json` into your n8n instance
2. Connect your Gmail account inside the workflow
3. Copy the Webhook URL from the workflow
4. Paste it into the Obsidian Post Webhook plugin settings
5. Activate the workflow in n8n

---

## 📋 How to Use

Add YAML frontmatter at the top of any Obsidian note like this:

```yaml
---
to: "recipient@example.com"
cc: "cc@example.com"
bcc: "bcc@example.com"
subject: "Your Subject Here"
sender-name: "Your Name"
send-replies-to: "replies@example.com"
---

Your note content goes here...
```

Then open the command palette in Obsidian (`Ctrl/Cmd + P`), search for **Send to Webhook**, and run it.

---

## 🔄 Workflow Overview

1. Obsidian sends the note content via Webhook to n8n
2. n8n checks if the request is a test or a real email
3. If attachments exist, they are processed and converted to binary files
4. The email is sent via Gmail with or without attachments
5. n8n responds back to Obsidian with a confirmation and timestamp

---

## 📁 Project Structure

```
send-emails-from-obsidian/
├── README.md
├── workflow.json
└── .gitignore
```

---

## 📄 License

MIT License — free to use and modify.
