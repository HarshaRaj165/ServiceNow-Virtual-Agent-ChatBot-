# 💬 ServiceNow-Virtual-Agent-ChatBot-

This project showcases the design, configuration, and customization of a **Virtual Agent** in ServiceNow, built within a Personal Developer Instance (PDI). The Virtual Agent is configured to handle IT support scenarios (e.g., Outlook issues) using conversational flows, topic blocks, and NLU (Natural Language Understanding) integration.

---

## 🚀 Features

- ✅ Virtual Agent setup with custom greeting, fallback, and topic flows  
- ✅ Integration with NLU model for intent and utterance-based conversation handling  
- ✅ Dynamic user responses, knowledge article linking, and automated incident creation  
- ✅ Custom branding and UI styling of the chat interface  
- ✅ Modular topic blocks to enable ticket creation and live agent support

---

## 🛠️ Tools & Technologies Used

| Tool / Platform               | Purpose                                                                 |
|------------------------------|-------------------------------------------------------------------------|
| **ServiceNow PDI**           | Platform to configure and test ServiceNow features                      |
| **Virtual Agent Designer**   | To design conversational flows (topics and blocks)                      |
| **NLU Workbench**            | To train Intents and Utterances for smart topic redirection             |
| **Service Portal**           | End-user portal to test chat and view knowledge articles or submit RITMs|
| **Flow Designer**            | Backend process automation (e.g., trigger workflows on intent)          |
| **Topic Blocks**             | Reusable flows for actions like "Create Incident", "Search Catalog"     |
| **JavaScript**               | Custom logic for incident creation using Script Actions                 |

---
---

## 📌 Key Modules Configured

- **Virtual Agent Setup:**  
  Configured using Conversational Interfaces Guided Setup.

- **NLU Model & Intents:**  
  Custom "IT Issues" model with intents like *Outlook issue*, *Teams issue*, etc.

- **Topic Blocks:**  
  Reusable "Create Incident" topic block with input mapping (caller, short description).

- **Portal Testing:**  
  Final flow tested in Service Portal with dynamic greeting and fallback search.

---

## 🧠 Functionalities Implemented

### 1. **Virtual Agent Configuration**
- Activated necessary plugins:
  - Glide Virtual Agent
  - ITSM Virtual Agent Conversations
- Enabled via Conversational Interface Guided Setup
- Customized greetings, fallback behavior, and branding

### 2. **Custom Topic: Outlook Issue**
- Created a topic named **Outlook Issue**
- Added keywords like “Outlook not working”, “Email issue”, etc.
- Configured user input (choice options), bot responses, and header cards

### 3. **Knowledge Article Integration**
- If issue is common (e.g., Outlook is slow), show a knowledge article
- Ask the user if the issue was resolved using Boolean choice

### 4. **Fallback Path: Create Incident or Live Agent**
- If issue not resolved, bot gives two options:
  - **Create Ticket**: Pass caller & short description to a Topic Block
  - **Live Agent Support**: Transfer to human agent (not shown in demo)

### 5. **Reusable Topic Block: Create Incident**
- Duplicated and customized OOTB Create Incident topic block
- Mapped input variables:
  - Caller (via sys_id)
  - Short description (user input)
- Used JavaScript to create incident via GlideRecord
- Sent confirmation + incident card (with RITM number, state, etc.)

### 6. **NLU Model & Training**
- Created a model named **IT Issues**
- Defined 2 intents: Outlook issue, Teams issue
- Added multiple utterances for each (up to 15)
- Trained and tested the model inside NLU Workbench
- Linked NLU model + Intent to Outlook topic for seamless redirection

### 7. **Branding & UI Customization**
- Customized:
  - Chat header text, logo, avatar
  - Colors for user and bot messages
  - Menu options, loading delays
- Live preview tested inside Guided Setup

---

## 🧪 Testing & Demo Steps

1. Navigate to Service Portal (`SP`)
2. Open the chat window
3. Type: `Outlook is not responding`
4. Bot triggers “Outlook Issue” topic (via NLU intent)
5. Select issue (e.g., “Outlook is slow”)
6. Bot shows KB article → asks if resolved
7. Click **No**, then choose **Create Ticket**
8. Describe issue (e.g., “Outlook crashes”)
9. Bot creates Incident and shows confirmation card

---

## 📸 Screenshots

>![image alt](https://github.com/HarshaRaj165/ServiceNow-Virtual-Agent-ChatBot-/blob/db32d9644619c20928f9c0624f6463f824c7285b/VA.png)
>![image alt](https://github.com/HarshaRaj165/ServiceNow-Virtual-Agent-ChatBot-/blob/d5df6407aa5300fa1518cd4534a68909d3acd5be/ChatBot.png)

---


## 🎯 Learning Outcomes

- Hands-on experience in ServiceNow's Virtual Agent & NLU
- Built a working chatbot with dynamic flows and ticketing
- Understood plugin activation, topic logic, and fallback handling
- Integrated machine learning concepts (Intent + Utterance training)
- Practiced script-based automation and flow reuse

---

🏁 Conclusion

This project successfully demonstrates the complete lifecycle of setting up and customizing a ServiceNow Virtual Agent with Natural Language Understanding (NLU), Incident Management integration, and Service Portal branding. It highlights my ability to configure ServiceNow features from scratch, implement conversational flows, train AI-driven intents, and connect automated processes with real ITSM workflows.
