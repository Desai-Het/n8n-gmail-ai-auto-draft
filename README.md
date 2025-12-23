# 📧 Gmail AI Draft Reply (n8n)

An **n8n-powered AI email assistant** that automatically categorizes incoming Gmail messages, applies the correct label, and **drafts a professional reply** — without sending it — allowing the user to review before final delivery.

---

## ✨ Features

- 📥 Triggers on **new incoming Gmail messages**
- 🏷️ **Automatically classifies emails** into predefined labels:
  - `Doubts`
  - `Sponsorship`
  - `Courses`
- 🧠 Uses an **AI Agent (OpenAI)** to understand email context
- 📝 **Generates a draft reply** with:
  - Proper subject
  - Clean, readable **HTML email body**
- 🛑 **Does NOT auto-send emails**
  - User reviews and sends manually from Gmail
- 🔄 Preserves the original **email thread**

---

## 🧩 Workflow Overview

1. **Gmail Trigger**  
   Listens for new incoming emails

2. **Get Message**  
   Fetches full email content

3. **AI Agent**  
   - Analyzes subject and body  
   - Selects the correct label  
   - Drafts a reply email  

4. **Structured Output Parser**  
   Ensures clean JSON output:
   - `label`
   - `label_id`
   - `subject`
   - `body`

5. **Add Label**  
   Applies the selected Gmail label

6. **Create Draft**  
   Saves the AI-generated reply as a Gmail draft

---

## ⚠️ Important Design Choice

> 🚨 **Emails are NOT sent automatically**

This workflow only **creates a draft**, ensuring:
- Human review before sending
- No accidental or incorrect replies
- Full control over final communication

---

## 🔐 Security Notes

- ❌ Do **NOT** commit real API keys
- ❌ Do **NOT** commit OAuth tokens
- ✅ Credentials are stored securely inside **n8n**
- ✅ The provided JSON file is **safe to share once sanitized**

---

## 🛠️ Setup Instructions

1. Import the workflow JSON into **n8n**
2. Configure credentials:
   - Gmail OAuth2
   - OpenAI API
3. Ensure Gmail labels exist:
   - `Doubts`
   - `Sponsorship`
   - `Courses`
4. Activate the workflow
5. Send a test email to your Gmail inbox

---

## 🧪 Recommended Testing

- Send different types of emails:
  - Questions / doubts
  - Business inquiries
  - Course-related messages
- Verify:
  - Correct label assignment
  - Draft content quality
  - Proper subject generation

---

## 🚀 Tech Stack

- **n8n**
- **Gmail API**
- **OpenAI (Chat Models)**
- **LangChain AI Agent**
- **Structured Output Parser**

---

## 📌 Use Case

Perfect for:
- Personal inbox automation
- Founders, educators, creators
- Anyone handling repetitive email replies
