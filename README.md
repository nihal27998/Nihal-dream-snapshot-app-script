# Nihal-dream-snapshot-app-script
# 🚀 AI Dream Snapshot Generator

An AI-powered Google Sheets automation tool that transforms Business Owner discovery call transcripts into structured **Dream Snapshots** using Google's Gemini AI.

The system extracts only the Business Owner's statements, analyzes their business situation across 12 dimensions, and generates a personalized business insight report automatically inside Google Sheets.

---

# 📌 Project Overview

The Dream Snapshot Generator is designed for business coaches, consultants, and sales teams who need quick insights from discovery calls.

Instead of manually analyzing long conversations, this tool uses Gemini AI to:

- Identify the actual Business Owner statements
- Remove sales representative conversations
- Understand business challenges and goals
- Classify the owner into 12 business dimensions
- Generate a detailed personalized snapshot
- Store the final report inside Google Sheets

---

# ✨ Features

## 🔹 Google Sheets Automation

- Adds a custom AI menu inside Google Sheets
- Processes the currently selected row
- Reads transcripts automatically from Column H
- Updates processing status in Column I
- Generates reports in Column J

---

## 🔹 AI Transcript Processing Pipeline

The application follows a three-stage AI workflow.

---

## Stage 1: Business Owner Statement Extraction

The AI identifies who the Business Owner is and extracts only their statements.

### Process:

```
Full Discovery Call Transcript
            |
            ↓
Remove BD/Salesperson Conversation
            |
            ↓
Business Owner Statements Only
```

Benefits:

- Removes sales noise
- Preserves owner's original words
- Creates clean input for analysis

---

# Stage 2: Business Classification

The extracted statements are analyzed using 12 fixed business dimensions.

| Dimension | Purpose |
|----------|---------|
| Q1 | Business performance understanding |
| Q2 | Team role suitability |
| Q3 | Decision-making approach |
| Q4 | Tracking and measurement habits |
| Q5 | Business vision |
| Q6 | Leadership approach |
| Q7 | Growth ambition |
| Q8 | Improvement priorities |
| Q9 | Business risks |
| Q10 | Learning approach |
| Q11 | Improvement stage |
| Q12 | Readiness level |

Each dimension contains:

- Structured code
- Simple explanation
- Human-readable display label

---

# Stage 3: Dream Snapshot Generation

The AI creates an owner-facing report containing:

- Business performance overview
- Team situation
- Decision-making style
- Current challenges
- Growth vision
- Improvement areas
- Risks of delaying action
- Readiness assessment
- Final business insight summary

---

# 🏗️ System Architecture

```
                 Google Sheet
                      |
                      |
          Discovery Call Transcript
                (Column H)
                      |
                      ↓
          Google Apps Script
                      |
                      ↓
             Gemini 2.5 Flash API
                      |
        ----------------------------
        |                          |
        ↓                          ↓
Owner Statement Extraction   Business Classification
        |                          |
        ----------------------------
                      |
                      ↓
          Dream Snapshot Generator
                      |
                      ↓
              Output in Sheet
                (Column J)
```

---

# 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| Google Apps Script | Backend automation |
| Google Sheets | Data storage interface |
| Gemini 2.5 Flash API | AI processing |
| JavaScript | Application logic |
| Google Workspace | Deployment platform |

---

# 📂 Google Sheet Format

The script requires this structure:

| Column | Content |
|--------|---------|
| H | Business Owner Transcript |
| I | Processing Status |
| J | Generated Dream Snapshot |

Example:

```
Column H → Transcript Input

Column I → Processing Status

Column J → AI Generated Output
```

---

# ⚙️ Installation & Setup

## Step 1: Create Google Sheet

Create a Google Sheet and keep the required columns:

```
H = Transcript
I = Status
J = Output
```

---

## Step 2: Open Apps Script

Go to:

```
Extensions → Apps Script
```

Paste the provided JavaScript code.

---

## Step 3: Configure Gemini API Key

Replace:

```javascript
const GEMINI_API_KEY = "";
```

with:

```javascript
const GEMINI_API_KEY = "YOUR_GEMINI_API_KEY";
```

Get your API key from:

```
https://aistudio.google.com/
```

---

## Step 4: Authorize Script

Run:

```
onOpen()
```

Allow permissions.

Refresh your Google Sheet.

A new menu will appear:

```
🚀 AI Tools

    └── Generate Dream Snapshot
```

---

# ▶️ How To Use

1. Add a discovery call transcript in Column H
2. Select the required row
3. Open:

```
🚀 AI Tools
        |
        └── Generate Dream Snapshot
```

4. Wait for processing

The status will update:

```
⏳ Processing...

        ↓

✅ Done
```

The generated Dream Snapshot will appear in Column J.

---

# 🔄 Complete Workflow

```
Input Transcript
        |
        ↓
Extract Owner Statements
        |
        ↓
Classify Business Situation
        |
        ↓
Generate Dream Snapshot
        |
        ↓
Save Report
```

---

# 🔐 Security Recommendations

Do not expose your Gemini API key publicly.

For production environments, store the key securely using:

```javascript
PropertiesService
.getScriptProperties()
.getProperty("GEMINI_API_KEY");
```

Avoid hardcoding API keys inside source files.

---

# ⚠️ Limitations

- Maximum transcript processing length is limited
- AI accuracy depends on transcript quality
- Speaker identification depends on conversation clarity
- Gemini API availability is required
- Long conversations may require chunk processing

---

# 🚀 Future Enhancements

Possible improvements:

- Automatic Zoom/Google Meet transcript import
- Speaker identification using AI diarization
- Batch transcript processing
- CRM integration
- Business analytics dashboard
- Email report generation
- Database storage
- Multi-user access control

---

# 📌 Use Cases

This tool can be used for:

- Business coaching analysis
- Sales discovery analysis
- Customer research
- Lead qualification
- Consulting preparation
- Client onboarding

---

# 👨‍💻 Author

AI automation project built using Google Apps Script and Gemini AI.

---

# 📄 License

This project is intended for educational and business automation purposes.
