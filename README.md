# Invoice Processing Workflow (n8n Automation)

An end-to-end automated invoice processing system built using **n8n**, **LlamaParse**, and AI-based information extraction. This workflow automatically detects new invoices from Google Drive, extracts structured financial data, and stores it in Google Sheets while organizing processed files.

---

## 🚀 Features

- 📥 Automatically detects new invoice files in Google Drive
- 🤖 Uses LlamaParse to convert invoices into clean markdown/text
- 🧠 AI-powered structured data extraction (invoice details, totals, vendor info)
- 📊 Stores extracted data in Google Sheets
- 📂 Moves processed files to a separate folder
- 🗑️ Deletes or archives original files after processing
- 🔁 Retry mechanism using wait & status check loop

---

## 🏗️ Tech Stack

- [n8n](https://n8n.io/) – Workflow automation platform
- Google Drive API – File storage & triggers
- Google Sheets API – Data storage
- LlamaParse (LlamaIndex) – Document parsing
- Groq LLM (Kimi model) – AI extraction engine

---

## ⚙️ Workflow Overview

1. **Trigger**: New file uploaded to Google Drive folder
2. **Download File**: Fetch invoice file from Drive
3. **Upload to LlamaParse**: Convert document into structured text
4. **Wait Loop**: Check processing status until completion
5. **Fetch Result**: Get markdown output
6. **AI Extraction**: Extract invoice fields using LLM
7. **Save Data**: Append structured data to Google Sheets
8. **Move File**: Transfer file to processed folder
9. **Cleanup**: Delete original file from unprocessed folder

---

## 📊 Extracted Fields

The system extracts the following invoice data:

- Invoice Number
- Invoice Date
- Due Date
- Vendor Name
- Vendor Address
- Client Name
- Line Items
- Subtotal
- Tax Amount
- Total Amount
- Currency
- Payment Terms

---

## 🔧 Setup Instructions

### 1. Clone Repository
```bash
git clone https://github.com/your-username/invoice-processing-workflow.git
```

### 2. Import Workflow in n8n
- Open n8n dashboard
- Click **Import Workflow**
- Upload JSON file

### 3. Add Credentials
Configure the following credentials:
- Google Drive OAuth2
- Google Sheets OAuth2
- LlamaParse API Key
- Groq API Key

### 4. Configure IDs
Replace placeholders:
- YOUR_UNPROCESSED_FOLDER_ID
- YOUR_PROCESSED_FOLDER_ID
- YOUR_GOOGLE_SHEET_ID

### 5. Activate Workflow
Turn on the workflow in n8n dashboard

---

## 🧠 AI Model

This workflow uses:
- **Groq API** with `moonshotai/kimi-k2-instruct`
- Prompt-based structured extraction for invoice parsing

---

## 📌 Use Case

Ideal for:
- Accounting automation
- Freelancers managing invoices
- Finance teams
- Small businesses
- Data entry automation

---

## 📈 Future Improvements

- Add email invoice ingestion
- Integrate OCR fallback
- Add database storage (PostgreSQL / MongoDB)
- Dashboard visualization
- Multi-currency support

---

## 🧑‍💻 Author

Built as a portfolio project for showcasing **AI + Automation + n8n workflow engineering skills**.

---

## ⭐ If you like this project

Give it a star ⭐ and feel free to fork & improve it!

