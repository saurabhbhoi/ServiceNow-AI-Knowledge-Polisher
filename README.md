# 🚀 ServiceNow AI Knowledge Polisher

![ServiceNow](https://img.shields.io/badge/Platform-ServiceNow-green) ![AI](https://img.shields.io/badge/AI-Google%20Gemini-blue) ![License](https://img.shields.io/badge/License-MIT-orange)

A "Plug-and-Play" ServiceNow utility that uses **Google Gemini 1.5 Flash** to instantly format, proofread, and enhance Knowledge Base articles. It creates professional HTML layouts and automatically generates data visualization charts from text data.

---

## ✨ Features

* **Zero "Pro" License Cost:** Works on Standard ServiceNow instances. No Integration Hub or "Now Assist" licenses required.
* **One-Click Polishing:** Turns rough notes into structured HTML (Headers, Lists, Paragraphs).
* **Auto-Charting:** Detects numerical data in text and generates visual Bar/Pie charts using [QuickChart.io](https://quickchart.io).
* **Strict Mode:** AI is configured to return *only* code, ensuring no conversational filler breaks your article.
* **Secure:** Uses your own API Key stored securely in a **System Property**, keeping it separate from the codebase.

## 🛠️ Prerequisites

1.  **ServiceNow Instance:** (PDI or Enterprise) running Vancouver or newer.
2.  **Google Gemini API Key:** Get a free key at [Google AI Studio](https://aistudio.google.com/).

## 📦 Installation

### Step 1: Import the Update Set
1.  Download the XML file from the `update-sets/` folder in this repository.
2.  In ServiceNow, navigate to **System Update Sets > Retrieved Update Sets**.
3.  Click the link **Import Update Set from XML** and upload the file.
4.  **Preview** and **Commit** the update set.

### Step 2: Configure API Key
1.  Navigate to **System Properties > All Properties** (or type `sys_properties.list` in the filter navigator).
2.  Search for the property named: `gemini.integration.api_key`.
3.  Paste your Google Gemini API Key into the **Value** field.
4.  Click **Update**.

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
| **Script Include** | `GeminiGlobalUtils` | Handles logic, constructs the prompts, and retrieves the API Key safely from System Properties. |
| **System Property** | `gemini.integration.api_key` | Stores the client's API Key securely so no code editing is required. |
| **UI Action** | `✨ AI Polish` | Client-side button on `kb_knowledge` table that triggers the process. |
| **REST Message** | `Gemini AI` | Configured endpoint for Google Generative Language API. |

---

## ⚠️ Disclaimer
This tool sends data to the Google Gemini API. Ensure you comply with your organization's data privacy policies regarding AI usage. Do not process PII (Personally Identifiable Information) without validation.

## 👤 Author
**Saurabh**
* ServiceNow Developer
* [LinkedIn Profile](https://www.linkedin.com/in/saurabh-bhoi-20sam/)
