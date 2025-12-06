# ServiceNow-AI-Knowledge-Polisher

# 🚀 ServiceNow AI Knowledge Polisher

![ServiceNow](https://img.shields.io/badge/Platform-ServiceNow-green) ![AI](https://img.shields.io/badge/AI-Google%20Gemini-blue) ![License](https://img.shields.io/badge/License-MIT-orange)

A "Plug-and-Play" ServiceNow utility that uses **Google Gemini 1.5 Flash** to instantly format, proofread, and enhance Knowledge Base articles. It creates professional HTML layouts and automatically generates data visualization charts from text data.

---

## ✨ Features

* **Zero "Pro" License Cost:** Works on Standard ServiceNow instances. No Integration Hub or "Now Assist" licenses required.
* **One-Click Polishing:** Turns rough notes into structured HTML (Headers, Lists, Paragraphs).
* **Auto-Charting:** Detects numerical data in text and generates visual Bar/Pie charts using [QuickChart.io](https://quickchart.io).
* **Strict Mode:** AI is configured to return *only* code, ensuring no conversational filler breaks your article.
* **Secure:** Uses your own API Key stored securely in System Properties (or Script Include).

## 🛠️ Prerequisites

1.  **ServiceNow Instance:** (PDI or Enterprise) running Vancouver or newer.
2.  **Google Gemini API Key:** Get a free key at [Google AI Studio](https://aistudio.google.com/).

## 📦 Installation

### Step 1: Import the Update Set
1.  Download the XML file from the `update-sets/` folder in this repository.
2.  In ServiceNow, navigate to **System Update Sets > Retrieved Update Sets**.
3.  Click **Import Update Set from XML** and upload the file.
4.  **Preview** and **Commit** the update set.

### Step 2: Configure API Key
1.  Open the `GeminiGlobalUtils` Script Include.
2.  Locate the line `var apiKey = 'PASTE_YOUR_API_KEY_HERE';`.
3.  Replace the placeholder with your actual Google Gemini API Key.
4.  Save the record.

*(Note: If using the System Property version, navigate to `sys_properties.list`, find `gemini.integration.api_key`, and paste your key there).*

---

## 🚀 How to Use

1.  Navigate to **Knowledge > Articles > Create New**.
2.  Type your rough notes into the **Text** field.
    * *Example:* "Server CPU usage report: Jan 80%, Feb 65%, Mar 90%."
3.  Click the **✨ AI Polish** button on the form header.
4.  Wait 3-5 seconds. The text will be replaced with a clean HTML table/list and a visual chart representing the data.

---

## 📂 Technical Components

| Component | Name | Description |
| :--- | :--- | :--- |
| **Script Include** | `GeminiGlobalUtils` | Handles API connection, Prompt Engineering, and Error Handling. |
| **UI Action** | `✨ AI Polish` | Client-side button on `kb_knowledge` table. |
| **REST Message** | `Gemini AI` | Configured endpoint for Google Generative Language API. |

---

## ⚠️ Disclaimer
This tool sends data to the Google Gemini API. Ensure you comply with your organization's data privacy policies regarding AI usage. Do not process PII (Personally Identifiable Information) without validation.

## 👤 Author
**[Your Name]**
* ServiceNow Developer
* [Link to your LinkedIn Profile]
