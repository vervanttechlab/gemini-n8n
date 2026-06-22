# COMPETENCY-BASED LEARNING MATERIAL (CBLM)

---

|  |  |
|---|---|
| **Qualification** | Automation Level III |
| **Unit of Competency** | Implementing Basic Automation Techniques Using AI Tools |
| **Module Title** | Implementing Basic Automation Techniques Using AI Tools |
| **Unit Code** | 1.2 |
| **Nominal Duration** | 18 Hours |
| **Tools/Platforms Used** | n8n · Gemini CLI · Kilo Code · Groq (free tokens) |
| **Learner's Name** | _________________________ |
| **Trainer's Name** | _________________________ |
| **Date Started** | ___________ &nbsp;&nbsp; **Date Finished** | ___________ |

---

## HOW TO USE THIS COMPETENCY-BASED LEARNING MATERIAL

Welcome to the module **Implementing Basic Automation Techniques Using AI
Tools**, part of the **Automation Level III** qualification. This module builds
on **UC1: Utilizing Generative AI**.

This unit of competency contains the knowledge, skills, and attitudes required to
**select AI-enabled automation tools, configure basic AI-driven workflows, and
monitor and update** those workflows — using a platform such as **n8n**
(running at http://localhost:5678).

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
| **1.2.1** | Select AI-enabled automation tools |
| **1.2.2** | Configure basic AI-driven workflows |
| **1.2.3** | Monitor and update workflows |

---

## LEARNING OUTCOME SUMMARY — UNIT OF COMPETENCY 2 (UC2)

**UNIT OF COMPETENCY:** Implementing Basic Automation Techniques Using AI Tools
**MODULE TITLE:** Implementing Basic Automation Techniques Using AI Tools

**LEARNING OUTCOMES:** Upon completion of this module, the learner must be able to:

1.2.1 Select AI-enabled automation tools.
1.2.2 Configure basic AI-driven workflows.
1.2.3 Monitor and update workflows.

**ASSESSMENT CRITERIA:**
1. Suitable AI-enabled automation tools are selected for a given task.
2. A basic AI-driven workflow is configured and runs successfully.
3. Data flows correctly between the steps/nodes of the workflow.
4. Workflows are monitored using execution logs.
5. Workflows are updated and improved based on results.

**CONDITIONS:** The learner must be provided with the following:
- Computer/laptop with internet access
- A running n8n instance (e.g., http://localhost:5678)
- Access to an AI model / API key (Gemini, Kilo, or Groq free tokens)
- Worksheets and writing materials

**ASSESSMENT METHOD:**
- Written test
- Demonstration with oral questioning
- Portfolio of completed workflows and worksheets

---

# LEARNING OUTCOME 1.2.1: SELECT AI-ENABLED AUTOMATION TOOLS

### Information Sheet 1.2.1

**What is automation?**
Automation makes tasks happen **without manual effort**. **AI-enabled
automation** adds an AI step (like generating or analyzing text) inside an
automated process.

**What is n8n?**
n8n is a **workflow automation tool**. You connect **nodes** (building blocks) to
automate tasks. By adding an **AI node**, you include generative AI inside a
workflow.

**Choosing the right tool — ask:**

| Question | Why it matters |
|----------|----------------|
| What task am I automating? | Match the tool to the job |
| Does it need AI? | Use an AI node/model only if needed |
| Is it free / within my tokens? | Stay within free limits |
| Can it connect my apps? | Integration support (email, sheets, chat) |

**Common AI-enabled tools:**

| Tool | Role in automation |
|------|--------------------|
| **n8n** | The workflow platform that connects everything |
| **Gemini / Groq** | The AI model that generates/analyzes content |
| **Kilo Code** | AI assistant for building/automating code tasks |

---

### 📝 Worksheet 1.2.1 — Select Tools

**Exercise A — Match Task to Tool**

| Task | Best Tool |
|------|-----------|
| Connect a trigger, an AI step, and email | _______________ |
| Generate the text content for a message | _______________ |
| Get AI help writing automation code | _______________ |

**Exercise B — Justify a Choice**
You must automate *"every morning, generate a quote and email it."* Which tools
would you select and why?
```
Tools chosen: ______________________________________________
Reason: ____________________________________________________
```

**Exercise C — Checklist**
List two questions you should ask before selecting an automation tool.
```
1. _________________________________________________________
2. _________________________________________________________
```

### ✅ Self-Check 1.2.1
1. What is AI-enabled automation?
2. What is the role of n8n in an automation?
3. Give two factors when choosing an automation tool.

**Answer Key 1.2.1**
1. Automation that includes an AI step (e.g., generating/analyzing content).
2. It is the platform that connects the steps/nodes together.
3. The task, whether AI is needed, cost/free limits, integrations (any two).

---

# LEARNING OUTCOME 1.2.2: CONFIGURE BASIC AI-DRIVEN WORKFLOWS

### Information Sheet 1.2.2

**Core n8n concepts:**

| Term | Meaning |
|------|---------|
| Node | A single step (trigger, action, or logic) |
| Trigger | What starts the workflow |
| Connection | The arrow passing data between nodes |
| Execution | One run of the workflow |
| Expression | `{{ }}` syntax to pull data from a previous node |

**Basic AI automation pattern:**
```
TRIGGER  →  AI STEP (process)  →  ACTION (output/deliver)
```

**Steps to configure a workflow in n8n:**
1. Create a new workflow.
2. Add a **trigger** (Manual or Schedule).
3. Add an **AI / HTTP Request node** and connect your AI service (Gemini/Groq).
4. Pass a prompt using an **expression**, e.g.
   `Summarize this: {{ $json.text }}`
5. Add an **action** node (e.g., Edit Fields, email).
6. **Test** the workflow and inspect each node's output.

---

### 📝 Worksheet 1.2.2 — Configure a Workflow

**Exercise A — Order the Build Steps (1–5)**

| Step | Order |
|------|-------|
| Test the workflow | ___ |
| Add a trigger | ___ |
| Add an action node | ___ |
| Create a new workflow | ___ |
| Add an AI node and pass a prompt | ___ |

**Exercise B — Build an AI Workflow (Hands-On)**
In n8n, build **Manual Trigger → AI/HTTP Request node**. Prompt: *"Write a
friendly welcome message for a new student."* Run it and record the output.
```
AI Output: _________________________________________________
___________________________________________________________
```

**Exercise C — Use an Expression**
Add an *Edit Fields* node and create a field `final_message` that combines text
with the AI output using an expression.
```
Expression: ________________________________________________
```

### ✅ Self-Check 1.2.2
1. Write the basic three-stage automation pattern.
2. What starts a workflow in n8n?
3. What does an expression `{{ }}` do?

**Answer Key 1.2.2**
1. Trigger → AI step (process) → Action (output).
2. A trigger node.
3. Pulls data from a previous node into the current one.

---

# LEARNING OUTCOME 1.2.3: MONITOR AND UPDATE WORKFLOWS

### Information Sheet 1.2.3

**Monitoring** means checking that your workflow runs correctly over time.
**Updating** means improving or fixing it based on what you observe.

**How to monitor in n8n:**
- Open the **Executions** tab to see each run (success or error).
- Click an execution to inspect the data at each node.
- Look for **failed nodes** (shown in red).

**Common updates:**

| Problem | Update |
|---------|--------|
| AI output is poor | Adjust the prompt (links to UC1 1.1.5) |
| Runs too often | Change the schedule |
| A node fails | Fix settings / add error handling |
| Output is biased/wrong | Review and correct (links to UC1 1.1.4 & 1.1.6) |

**Best practices:**
- **Test before activating** so it doesn't run incorrectly.
- **Turn off** test workflows when done.
- **Verify AI output** before it is delivered.

---

### 📝 Worksheet 1.2.3 — Monitor & Update

**Exercise A — Monitor (Hands-On)**
Add a **Schedule Trigger** to your workflow (every 1 minute for testing),
activate it, then open the **Executions** tab.
```
Number of executions seen: _______
Any failures? (Yes/No): _______
```
> Remember to turn the workflow **OFF** after testing.

**Exercise B — Diagnose & Update**
For each symptom, write what you would update.

| Symptom | Your Update |
|---------|-------------|
| AI message is too generic | _______________ |
| Workflow runs every minute (too often) | _______________ |
| A node shows a red error | _______________ |

**Exercise C — Improve Your Workflow**
Make one improvement to your workflow and describe the before/after.
```
Change made: _______________________________________________
Result/Improvement: ________________________________________
```

### ✅ Self-Check 1.2.3
1. Where do you check whether a workflow ran successfully in n8n?
2. Give one reason you might update a workflow.
3. Why test before activating a workflow?

**Answer Key 1.2.3**
1. The Executions tab.
2. Poor AI output, wrong schedule, a failing node, biased output (any one).
3. To make sure it works correctly and does not run with errors.

---

## PERFORMANCE CRITERIA CHECKLIST (UC2)

To be completed by the **Trainer/Assessor**.

| The learner is able to… | Yes | No |
|--------------------------|-----|----|
| Select suitable AI-enabled automation tools for a task | ☐ | ☐ |
| Justify the choice of tools | ☐ | ☐ |
| Configure a basic AI-driven workflow in n8n | ☐ | ☐ |
| Pass data to an AI node using an expression | ☐ | ☐ |
| Monitor workflow executions and identify failures | ☐ | ☐ |
| Update and improve a workflow based on results | ☐ | ☐ |

**Overall Result:** ☐ Competent &nbsp;&nbsp; ☐ Not Yet Competent

**Trainer's Feedback:**
```
___________________________________________________________
```

**Learner's Signature:** ______________  **Date:** __________
**Trainer's Signature:** ______________  **Date:** __________

---

*End of Unit of Competency 2 — Implementing Basic Automation Techniques Using AI Tools*
