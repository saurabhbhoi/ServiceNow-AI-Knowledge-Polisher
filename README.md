# 🚀 ServiceNow AI Knowledge Polisher

### 🔗 **Download the Update Set:** [Get it here on Topmate](https://topmate.io/srx_b/1837084)

![ServiceNow](https://img.shields.io/badge/Platform-ServiceNow-green) ![AI](https://img.shields.io/badge/AI-Google%20Gemini-blue) ![License](https://img.shields.io/badge/License-MIT-orange)

A "Plug-and-Play" ServiceNow utility that uses **Google Gemini 1.5 Flash** to instantly format, proofread, and enhance Knowledge Base articles. It creates professional HTML layouts and automatically generates data visualization charts directly from your text data.

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
1.  **Download** the XML file from the link above (or the `update-sets/` folder).
2.  In ServiceNow, navigate to **System Update Sets > Retrieved Update Sets**.
3.  Click the link **Import Update Set from XML** and upload the file.
4.  **Preview** and **Commit** the update set.

### Step 2: Configure API Key
1.  Navigate to **System Properties > All Properties** (or type `sys_properties.list` into the navigator).
2.  Search for the property name: `gemini.integration.api_key`.
3.  Paste your **Google Gemini API Key** into the **Value** field.
4.  Click **Update**.

---

## 🚀 How to Use

1.  Navigate to **Knowledge > Articles > Create New**.
2.  Type your rough notes into the **Text** field.
    * *Example:* `"Server CPU usage report: Jan 80%, Feb 65%, Mar 90%."`
3.  Click the **✨ AI Polish** button on the form header.
4.  Wait 3–5 seconds. The content will automatically convert into clean HTML + a generated visual chart.

---

## 📂 Technical Components

| Component | Name | Description |
| :--- | :--- | :--- |
| **Script Include** | `GeminiGlobalUtils` | Builds prompts, processes AI responses, and retrieves API Key safely. |
| **System Property** | `gemini.integration.api_key` | Secure storage for your Gemini API Key. |
| **UI Action** | `✨ AI Polish` | Button on `kb_knowledge` table to trigger polishing. |
| **REST Message** | `Gemini AI` | Configuration for the Google Generative Language API. |

---

## ⚠️ Disclaimer
This tool sends data to the Google Gemini API. Please ensure you comply with your organization’s AI and data privacy guidelines. Avoid processing PII (Personally Identifiable Information) unless authorized.

## 👤 Author
**Saurabh**
* ServiceNow Developer
* [LinkedIn Profile](https://www.linkedin.com/in/saurabh-bhoi-20sam/)
