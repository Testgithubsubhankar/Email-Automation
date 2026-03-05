# AI-Powered Email Automation & Quotation Extraction System
Sending Mail From Google sheet and Extract PDF,Xlsx,body message from the mail and update it in tracker

## 🚀 Project Overview

This project automates the **complete email-to-data workflow** by integrating **Gmail, AI processing, and Google Sheets** using **n8n automation**.

The system automatically reads incoming emails, extracts quotation information from **email body, PDF, or Excel attachments**, processes the data using **AI**, and stores structured results in **Google Sheets** for further business analysis.

The goal of this project is to eliminate **manual quotation entry**, reduce **human errors**, and create a **fully automated procurement data pipeline**.

---

# ⚙️ Workflow Architecture

The automation workflow performs the following steps:

### 1️⃣ Gmail Monitoring

A **Gmail Trigger** continuously monitors incoming emails in the purchase mailbox.

* Detects new quotation emails
* Downloads all attachments automatically
* Captures email metadata (sender, subject, date)

---

### 2️⃣ Email Cleaning & Pre-Processing

Custom JavaScript nodes process the raw email data:

* Remove unnecessary HTML tags
* Convert email body to clean text
* Filter out image attachments
* Separate relevant documents

This ensures the AI receives **clean and structured input data**.

---

### 3️⃣ Document Type Detection

Attachments are automatically classified based on MIME type:

* **Excel Files (.xlsx / .xls)**
* **PDF Quotations**
* **Email Body Content**

Each type follows a dedicated processing pipeline.

---

### 4️⃣ Data Extraction

Files are processed using extraction tools:

| File Type  | Processing         |
| ---------- | ------------------ |
| Excel      | Table extraction   |
| PDF        | Text parsing       |
| Email Body | Direct AI analysis |

The extracted content is converted into a **machine-readable format**.

---

### 5️⃣ AI-Based Quotation Intelligence

An AI Agent processes the extracted text and identifies key commercial details:

* Vendor Name
* Item Names
* Quantity
* Unit Rate
* Discount Percentage
* Line Item Amount
* Final Quotation Amount

The AI also performs **internal validation and calculations** to ensure accuracy.

---

### 6️⃣ Data Structuring

The AI returns the results in **strict JSON format**, which is normalized using JavaScript logic to ensure consistency.

Example Output:

```json
{
  "vendorName": "ABC Industrial Supplies",
  "quotationAmount": 24500,
  "items": [
    {
      "itemName": "Hydraulic Pump",
      "quantity": 2,
      "unitRate": 10000,
      "discountPercent": 5,
      "lineAmount": 19000
    }
  ]
}
```

---

### 7️⃣ Google Sheets Integration

The final structured data is automatically appended into **Google Sheets**, creating a real-time **quotation database**.

Stored fields include:

* Vendor Name
* Item Name
* Quantity
* Unit Rate
* Discount
* Total Amount

This allows teams to easily perform:

* Vendor comparison
* Price analysis
* Procurement tracking

---

# 🧠 Technologies Used

* **n8n** – Workflow Automation
* **Gmail API** – Email ingestion
* **OpenAI / AI Agent** – Intelligent data extraction
* **JavaScript** – Data processing and transformation
* **Google Sheets API** – Data storage and reporting
* **PDF & Excel Parsers** – Document extraction

---

# 🎯 Key Features

✅ Automated email monitoring
✅ Multi-format document processing (Email, PDF, Excel)
✅ AI-powered quotation understanding
✅ Automatic calculation validation
✅ Real-time data storage in Google Sheets
✅ Fully serverless automation workflow

---

# 💡 Real Business Impact

This system can help organizations:

* Reduce **manual data entry by 90%**
* Speed up **quotation comparison**
* Improve **procurement decision making**
* Maintain a **centralized quotation database**

---

# 🔒 Privacy & Security

Sensitive company data has been **removed and anonymized** in this repository.
The workflow demonstrates the **technical architecture and automation logic** only.

---


