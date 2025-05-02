# Customer Support Email Automation System

Automate customer support emails using AI agents and a Langgraph-driven workflow to categorize, synthesize, draft, and verify responses.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [How It Works](#how-it-works)
4. [System Flowchart](#system-flowchart)
5. [Tech Stack](#tech-stack)
6. [Setup](#setup)
7. [Running the Application](#running-the-application)
8. [Customization](#customization)
9. [Contributing](#contributing)

---

## Introduction
In today’s fast-paced environment, businesses must provide quick, accurate, and personalized customer support to maintain satisfaction and loyalty. Manual processing of high email volumes can lead to delays, inconsistencies, and increased operational costs.

This Customer Support Email Automation System leverages multiple AI agents orchestrated by Langgraph and Langchain, integrating RAG (Retrieval-Augmented Generation) for precise information retrieval. The result is an end-to-end automated workflow that monitors incoming emails, categorizes them, drafts high-quality responses, verifies content, and dispatches replies—all with minimal human intervention.

---

## Features

- **Email Inbox Management**
  - Continuous monitoring of Gmail inbox via the Gmail API
  - Automatic categorization into Customer Complaint, Product Inquiry, Customer Feedback, or Unrelated
  - Auto-handling of irrelevant emails to reduce noise

- **AI Response Generation**
  - Tailored draft creation for complaints and feedback using Langgraph
  - RAG-powered retrieval for accurate answers to product/service queries
  - Personalized email content based on customer context

- **Quality Assurance**
  - Automated checks for formatting, tone, and relevance
  - Ensures each email meets brand guidelines before sending

---

## How It Works

1. **Email Monitoring**: Polls Gmail inbox for new messages using the Gmail API.  
2. **Categorization**: AI agents classify each email into predefined categories.  
3. **Synthesis & Drafting**:  
   - Complaints/Feedback: Generates empathetic, solution-oriented drafts.  
   - Inquiries: Uses RAG to fetch data from internal documents and formulates precise replies.  
4. **Quality Assurance**: Each draft undergoes automated review for grammar, style, and accuracy.  
5. **Dispatch**: Sends approved responses via Gmail API, ensuring timely communication.

---

## System Flowchart

[View detailed workflow on Mermaid Live](https://mermaid.live/edit#pako:eNqllEuP2jAQx7-KZa6AgAB5HFrxFlJBXbarIsIeTDwBi2CntrPAEr57TRIoW_Wwojk585_fvJLxCQeCAvZwGIl9sCFSox_9JUfm6fgTwZkWEo0mnfE3NOYrcXgtNFSpfEHd01jlZjTYxfr49Zyr3YuaTgWawt4ohEUqRQt_wCn6LkUASr3eOw5FYpQXTrjagwR6Q3p-j2hYC8neITcWXC_jXriEyDjQFHXv7b1EabEDiXpiF0eEcY1ME0MAuiLBNkV9_6dk2uidNXD9IaQpjyaBRgP-K2HymKKB_3zkegPqUsJTApKBQqEJN-uMCnKQzWLuj0CjTtYCCqXY3XnMM49_pu1n0tA3iUU4A0L_0odZWZ04luINUjTyn4HTD7PIPaamO4Vm8MYUE9z0mIujQjzonMkmlUtKHyMwHzJkUeSVQjcsKy3FFryS4zjFubJnVG-8RnwoByIS0ivVarV7vFvgq9Uf3LKsz-K9a_bV6hG8f80ePoQP_i_78DY69xF8VOBu-BA-v2Z_DF8UOKX08zguY7NW5j-i5sI4XcItsdmNHSyxZ46UyO0SL_nZ-JFEC7M5Afa0TKCMpUjWG-yFJFLmLYmp2ds-I2tJdjdrTDj2TviAvUbLrjYtt2G1XLdVr7XtZhkfjbnqNJyW4zZt17LdpuO0z2X8LoQJUau6rbbt2la7btmWW6s3s3iLTMxLAHq5zCb5dRcIHrI1Pv8GXQeX4g)

---

## Tech Stack

- **Langchain & Langgraph**: AI agent orchestration  
- **Langserve (FastAPI)**: API layer for deployment  
- **Groq & Gemini APIs**: Access to LLMs and embeddings  
- **Google Gmail API**: Email integration  

---

## Setup

1. **Clone the repository**
   ```sh
   git clone https://github.com/kaymen99/langgraph-email-automation.git
   cd langgraph-email-automation
   ```
2. **Create & activate virtual environment**
   ```sh
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```
3. **Install dependencies**
   ```sh
   pip install -r requirements.txt
   ```
4. **Configure environment variables**
   Create a `.env` file with:
   ```env
   MY_EMAIL=your_email@gmail.com
   GROQ_API_KEY=your_groq_api_key
   GOOGLE_API_KEY=your_gemini_api_key
   ```
5. **Enable Gmail API**
   Follow Google's [Python Quickstart Guide](https://developers.google.com/gmail/api/quickstart/python).

---

## Running the Application

- **Start the automation workflow**
  ```sh
  python main.py
  ```
- **Deploy as API**
  ```sh
  python deploy_api.py
  ```
  Access API docs at `http://localhost:8000/docs` and the Langserve playground at `/playground`.

---

## Customization

- Modify agent logic in the `src/Nodes` class and update prompts in `src/prompts`.
- Add or update data in the `data/` folder and rebuild the vector index:
  ```sh
  python create_index.py
  ```

---

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for improvements, bug fixes, or new features.
