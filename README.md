# 📄 AI Resume Screening Agent

### 1. Overview
This project is an automated AI Agent designed to streamline the recruitment process. It allows HR managers to upload candidate resumes (PDF) alongside a specific Job Description. The agent uses AI to read the resume, compare it against the job requirements, and strictly rank the candidate with a match score (0-10) and a summary reason. All results are automatically logged to a Google Sheet.

[cite_start]This agent was built as part of the **48-Hour AI Agent Development Challenge** under **Category 1: People & HR**[cite: 13].

### 2. Features
* **Automated Interface:** A public web form for easy data entry (built via n8n Form Trigger).
* **PDF Analysis:** Automatically extracts raw text from PDF resumes using n8n's binary tools.
* **Intelligent Scoring:** Uses OpenAI (GPT-4o-mini) to analyze skills and experience against the job description.
* **Database Logging:** Automatically saves Candidate Name, Match Score, and Reasoning to Google Sheets.
* **Real-time Feedback:** Provides instant analysis without manual reading.

### 3. Architecture
**User (Web Form)** -> **Extract Text (PDF)** -> **AI Analysis (OpenAI)** -> **Google Sheets (Database)**

### 4. Tech Stack
* **Orchestration:** n8n (Workflow Automation)
* [cite_start]**AI Model:** OpenAI GPT-4o-mini [cite: 23]
* [cite_start]**Database:** Google Sheets [cite: 27]
* **Input Handling:** n8n Form Trigger

### 5. Setup & Run Instructions
To run this agent locally or in your own n8n instance:

1.  **Prerequisites:**
    * An active n8n instance (Cloud or Self-Hosted).
    * An OpenAI API Key.
    * A Google Cloud account (for Sheets integration).

2.  **Installation:**
    * Download the `resume screening agent.json` file from this repository.
    * Open n8n and click **"Import Workflow"**.
    * Select the `.json` file.

3.  **Configuration:**
    * **OpenAI Node:** Double-click the OpenAI node and add your API Credential.
    * **Google Sheets Node:** Connect your Google account and select a blank sheet with columns: `Name`, `Score`, `Reason`, `Date`.
    * **Form Trigger:** Ensure the form is set to "Active" to generate the public URL.

4.  **Running the Agent:**
    * Toggle the workflow to **Active** (Green).
    * Use the **Production URL** provided by the Form Trigger node to submit resumes.

### 6. Limitations
* Currently accepts PDF files only.

---
*Submitted for the AI Agent Development Challenge.*