# COMPETENCY-BASED LEARNING MATERIAL (CBLM)

---

|  |  |
|---|---|
| **Qualification** | Generative AI Fundamentals |
| **Unit of Competency** | Build AI Chatbots and Agents |
| **Module Title** | AI Chatbots & Agents |
| **Unit Code** | 1.1.5 |
| **Nominal Duration** | 14 Hours |
| **Learner's Name** | _________________________ |
| **Trainer's Name** | _________________________ |
| **Date Started** | ___________ &nbsp;&nbsp; **Date Finished** | ___________ |

---

## HOW TO USE THIS COMPETENCY-BASED LEARNING MATERIAL

Welcome to the module **AI Chatbots & Agents**. This module builds on
UC1–UC3 and applies them to building conversational AI inside an automation
platform such as **n8n**.

The unit of competency *"Build AI Chatbots and Agents"* contains the knowledge,
skills, and attitudes required for a learner to design a chatbot, give it memory
and tools, and build a simple AI agent that can take actions.

You are required to go through a series of learning activities. If you have
questions, please ask your trainer for assistance. Follow these steps:

1. Read the **Information Sheets** and answer the **Self-Checks**.
2. Compare your answers with the **Answer Keys** at the end of each section.
3. Perform the **Task/Worksheet Exercises** on a computer with n8n running.
4. Have your trainer evaluate your output using the **Performance Criteria
   Checklist**.

A certificate of achievement will be awarded once all competencies are
satisfactorily demonstrated.

---

## LIST OF LEARNING OUTCOMES

| LO No. | Learning Outcome |
|--------|------------------|
| **LO1** | Design a chatbot conversation flow |
| **LO2** | Add memory and context to a chatbot |
| **LO3** | Build a basic AI agent with tools |

---

## LEARNING OUTCOME SUMMARY — UNIT OF COMPETENCY 4 (UC4)

**UNIT OF COMPETENCY:** Build AI Chatbots and Agents
**MODULE TITLE:** AI Chatbots & Agents

**LEARNING OUTCOMES:**
Upon completion of this module, the learner must be able to:

1. Design a chatbot conversation flow with a clear purpose and persona.
2. Add memory and context so the chatbot remembers a conversation.
3. Build a basic AI agent that can use tools to take actions.

**ASSESSMENT CRITERIA:**

1. A chatbot purpose, persona, and system prompt are defined.
2. A working chat workflow is built and responds correctly.
3. Conversation memory is added so context is retained.
4. The difference between a chatbot and an agent is explained.
5. A basic agent that uses at least one tool is built and tested.

**CONDITIONS:** The learner must be provided with the following:
- Computer/laptop with internet access
- A running n8n instance (e.g., http://localhost:5678)
- Access to an AI model / API key
- Worksheets and writing materials

**ASSESSMENT METHOD:**
- Written test
- Demonstration with oral questioning
- Portfolio of completed chatbot/agent workflows

---

# LEARNING OUTCOME 1: DESIGN A CHATBOT CONVERSATION FLOW

### Information Sheet 1.1

**What is a chatbot?**
A chatbot is an AI program that holds a conversation with a user through text. A
good chatbot has a clear **purpose**, a **persona**, and a **system prompt**.

| Part | Meaning | Example |
|------|---------|---------|
| **Purpose** | What it helps with | "Answer questions about a school" |
| **Persona** | Its personality/tone | "Friendly and patient" |
| **System prompt** | Hidden instructions that set its behavior | "You are SchoolBot…" |

**System prompt example:**
```
You are SchoolBot, a friendly assistant for ABC College.
Only answer questions about enrollment, schedules, and courses.
If you don't know, politely say so.
```

**Basic chat flow in n8n:**
```
Chat Trigger  →  AI Model (with system prompt)  →  Reply
```

---

### 📝 Worksheet 1.1 — Design a Chatbot

**Exercise A — Plan Your Bot**
Design a chatbot of your choice. Fill in:

| Item | Your Answer |
|------|-------------|
| Bot name | _______________ |
| Purpose | _______________ |
| Persona / tone | _______________ |

**Exercise B — Write a System Prompt**
Write a complete system prompt for your bot (purpose + rules + tone).

```
___________________________________________________________
___________________________________________________________
___________________________________________________________
```

**Exercise C — Build a Simple Chatbot**
In n8n, build **Chat Trigger → AI Model node** and paste your system prompt.
Chat with it and record one question and its reply.

```
You asked: _________________________________________________
Bot replied: _______________________________________________
```

---

### ✅ Self-Check 1.1

1. What are the three parts of a well-designed chatbot?
2. What does a system prompt do?
3. Why should a chatbot admit when it doesn't know something?

**Answer Key 1.1**
1. Purpose, persona, system prompt.
2. Sets the chatbot's hidden behavior, rules, and tone.
3. To avoid giving false information (reduces hallucinations).

---

# LEARNING OUTCOME 2: ADD MEMORY AND CONTEXT TO A CHATBOT

### Information Sheet 2.1

**Why memory matters:**
Without memory, a chatbot forgets every previous message. Memory lets it follow
a conversation — e.g., remembering your name after you said it.

| Without memory | With memory |
|----------------|-------------|
| "What's my name?" → "I don't know." | "What's my name?" → "You're Ana." |

**How memory works (simple view):**
The conversation history is stored and sent back to the AI with each new message,
so it always has the context.

**In n8n:** add a **Memory** node (e.g., a buffer/window memory) connected to your
AI model so recent messages are remembered during the session.

**Context window:** AI models can only "remember" a limited amount of text at
once. Very long chats may need summarizing.

---

### 📝 Worksheet 2.1 — Memory & Context

**Exercise A — Test Memory**
Without memory: tell the bot your name, then in a new message ask "What's my
name?" Record the result. Then add a Memory node and repeat.

| Setup | Bot's answer to "What's my name?" |
|-------|-----------------------------------|
| No memory | _______________ |
| With memory | _______________ |

**Exercise B — Explain the Difference**
In your own words, explain why the bot's answer changed after adding memory.

```
___________________________________________________________
___________________________________________________________
```

**Exercise C — Context Window**
Answer the following:

```
1. What is a context window?
   _______________________________________________________

2. What can you do if a conversation gets too long for the model?
   _______________________________________________________
```

---

### ✅ Self-Check 2.1

1. What happens to a chatbot with no memory?
2. How does conversation memory work in simple terms?
3. What is a context window?

**Answer Key 2.1**
1. It forgets all previous messages.
2. The chat history is sent back to the AI with each new message.
3. The limited amount of text a model can consider at once.

---

# LEARNING OUTCOME 3: BUILD A BASIC AI AGENT WITH TOOLS

### Information Sheet 3.1

**Chatbot vs. Agent:**

| Chatbot | AI Agent |
|---------|----------|
| Only talks/answers | Talks **and takes actions** |
| No tools | Uses **tools** (search, calculator, send email, call an API) |
| Passive | Decides which tool to use to reach a goal |

**A tool** is an ability you give the agent — for example, a calculator tool, a
web-search tool, or a "send email" tool. The agent reads the request, decides
which tool to use, runs it, and replies with the result.

**Agent flow (simple):**
```
User request → Agent (AI decides) → uses a Tool → returns result
```

**In n8n:** use an **AI Agent node** and attach **tool nodes** (e.g., a
calculator, an HTTP request, Google Sheets) for the agent to call.

---

### 📝 Worksheet 3.1 — Build an Agent

**Exercise A — Chatbot or Agent?**
Mark each as **Chatbot** or **Agent**.

| Scenario | Answer |
|----------|--------|
| Answers FAQ questions only | __________ |
| Looks up live weather and emails it to you | __________ |
| Calculates a total and saves it to a sheet | __________ |
| Chats about general topics | __________ |

**Exercise B — Build a Tool-Using Agent**
In n8n, build an **AI Agent node** with a **Calculator tool** attached. Ask it a
math question that requires the tool. Record the interaction.

```
You asked: _________________________________________________
Tool used: _________________________________________________
Agent's answer: ____________________________________________
```

**Exercise C — Design Your Own Agent**
Plan a simple agent. What is its goal, and which one tool does it need?

```
Agent goal: ________________________________________________

Tool needed: _______________________________________________

How it helps the user: _____________________________________
```

---

### ✅ Self-Check 3.1

1. What is the main difference between a chatbot and an agent?
2. What is a "tool" in the context of an AI agent?
3. Give one example of a useful tool for an agent.

**Answer Key 3.1**
1. A chatbot only talks; an agent also takes actions using tools.
2. An ability/function the agent can call to do a task.
3. *(e.g.,)* calculator, web search, send email, call an API.

---

## PERFORMANCE CRITERIA CHECKLIST (UC4)

To be completed by the **Trainer/Assessor**.

| The learner is able to… | Yes | No |
|--------------------------|-----|----|
| Define a chatbot's purpose, persona, and system prompt | ☐ | ☐ |
| Build a working chatbot that responds correctly | ☐ | ☐ |
| Add memory so the chatbot retains context | ☐ | ☐ |
| Explain the difference between a chatbot and an agent | ☐ | ☐ |
| Build a basic agent that uses at least one tool | ☐ | ☐ |
| Test the agent and verify its output | ☐ | ☐ |

**Overall Result:** ☐ Competent &nbsp;&nbsp; ☐ Not Yet Competent

**Trainer's Feedback:**
```
___________________________________________________________
```

**Learner's Signature:** ______________  **Date:** __________
**Trainer's Signature:** ______________  **Date:** __________

---

*End of Unit of Competency 4 (UC4) — Build AI Chatbots and Agents*
