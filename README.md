# n8n-basic-linkedIn-content-creation-workflow
# 🚀 AI LinkedIn Content Creator (n8n Automation)

Automate your LinkedIn content creation using **n8n + Tavily Search API + OpenAI**.

This workflow:
- Pulls a topic from Google Sheets
- Researches it using Tavily Search
- Generates a high-quality LinkedIn post using OpenAI
- Updates the sheet with the final post
- Marks the status as `created`

---

## 📌 Overview

This automation is designed for:
- Founders
- Personal brands
- Marketers
- Consultants
- Content creators

It transforms a simple topic idea into a polished, engagement-ready LinkedIn post — automatically.

---

## 🔁 How the Workflow Works

### 1️⃣ Trigger
- Manual Trigger (Execute workflow)
- OR Scheduled Trigger (Daily at 9 AM)

### 2️⃣ Fetch Topic from Google Sheets
- Finds the first row where: Status = "TO do"
- Retrieves the `Topic` field

### 3️⃣ Web Research via Tavily API
- Searches: search the web for {{Topic}}
- Pulls top 3 relevant article summaries

### 4️⃣ AI Content Generation (OpenAI)
- Model used: `gpt-5-mini`
- AI Agent:
- Synthesizes (does NOT summarize)
- Writes 150–300 word post
- Adds 3–6 relevant emojis
- Adds 5–8 strategic hashtags
- Uses professional tone
- Ends with light engagement CTA

### 5️⃣ Update Google Sheet
- Updates:
- `Status` → `created`
- `content` → Generated LinkedIn post

---

## 📂 Google Sheets Structure

Your sheet must contain these columns:

| Topic | Status | content |
|-------|--------|----------|
| AI in Healthcare | TO do | |
| Future of Remote Work | TO do | |

### Status Flow:
- `TO do` → Processed
- `created` → Post generated

---

## ⚙️ Setup Instructions

### 1️⃣ Import Workflow
1. Open n8n
2. Go to **Workflows**
3. Click **Import**
4. Upload: linkedin content creator workflow.json


---

### 2️⃣ Configure Credentials

#### 🔹 Google Sheets OAuth2
- Connect your Google account
- Ensure sheet access is granted

#### 🔹 OpenAI API
- Add your OpenAI API key
- Select model: gpt-5-mini


#### 🔹 Tavily API
- Create account at Tavily
- Replace the Authorization header:
