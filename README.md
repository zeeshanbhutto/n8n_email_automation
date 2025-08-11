# 📧 n8n Email Automation Workflow

This repository contains an **n8n workflow** for sending personalized email invitations for **Tech CEOs invition**.  
The current workflow:
- Uses **Groq AI** for generating dynamic content in a simple chat memory setup.
- Reads recipient details from a Google Sheet.
- Sends emails via **Gmail**.
- Triggered via **n8n chat interface** (`When chat message received`).

⚠ **Note:** Gmail Trigger (for automatic reply capture) and responses spreadsheet logging are **not yet implemented** in this version.

---

## ✨ Features
- **AI-Powered Email Content** – Uses **Groq AI** for conversational content generation.
- **Memory Buffer** – Maintains context in conversations using `Simple Memory`.
- **Google Sheets Integration** – Reads recipient data from a specified sheet.
- **Gmail Sending** – Sends customized invitation emails.
- **Secure Setup** – Credentials are not stored in the repository.

---

## 📂 Project Structure
My_workflow_cleaned.json # Safe workflow export without credentials
.env.example # Example environment variables file
.gitignore # Prevents sensitive files from being committed

yaml
Copy
Edit

---

## 🚀 Setup Instructions

### 1️⃣ Clone the Repository

git clone https://github.com/zeeshanbhutto/n8n-email-automation.git
cd n8n-email-automation
2️⃣ Install n8n
bash
Copy
Edit
npm install n8n -g
(Or use Docker if preferred)

3️⃣ Configure Environment Variables
Duplicate .env.example → rename it to .env.

Fill in your API keys and OAuth credentials:

env
Copy
Edit
GMAIL_CLIENT_ID=your_gmail_client_id
GMAIL_CLIENT_SECRET=your_gmail_client_secret
GMAIL_REFRESH_TOKEN=your_refresh_token

GOOGLE_SHEETS_CLIENT_ID=your_google_sheets_client_id
GOOGLE_SHEETS_CLIENT_SECRET=your_google_sheets_client_secret
GOOGLE_SHEETS_REFRESH_TOKEN=your_refresh_token

GROQ_API_KEY=your_groq_api_key
4️⃣ Import Workflow in n8n
Open n8n editor (n8n start).

Import My_workflow_cleaned.json.

Link your credentials from .env in n8n’s Credentials Manager.

5️⃣ Run Workflow
Trigger via chat message in n8n UI.

Workflow will fetch data from Google Sheets and send invitations via Gmail.

🔒 Security
.env contains all credentials and must never be committed.

.gitignore ensures sensitive files stay local.

Public repo contains .env.example for reference only.

📌 Roadmap
 Add Gmail Trigger to capture replies.

 Log responses in a separate Google Sheet.

 Automate follow-up email sending.

📜 License
MIT License – feel free to use and modify.

🤝 Contributing
PRs and feature suggestions are welcome.
For major changes, please open an issue to discuss what you would like to change.

Author: Zeeshan Bhutto
