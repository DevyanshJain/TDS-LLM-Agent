
# 🔥 Browser LLM Agent – Proof of Concept

This project is a **lightweight demo** showing how a **language model agent** can live entirely in the browser and still handle more than text. The agent can reason in natural language, call external tools like search engines or custom APIs, and even run live JavaScript snippets in a sandbox.

Think of it as a starter kit for experimenting with “LLMs that act.”


---

## ✨ Highlights

✅ **🎛 Pick Your Model Provider**  
- Works with AI Pipe Proxy API (default), plus optional OpenAI, Gemini, Claude, and others.
- Simple dropdown to swap between models in real time.  

✅ **🔄 Reasoning Loop Agent**  
- Agent keeps looping: analyze → call tool → reflect → continue.
- Uses OpenAI-style function calling to trigger tools cleanly. 

✅ **🛠 Built-in Tools**  
- 🔎 Web Search (Google snippets) – grab quick context.
- 🔗 AI Pipe Workflows – chain AI processes flexibly.
- ⚡ JavaScript Sandbox – run small JS safely inside the browser.

✅ **🎨 Minimal but Usable UI**  
- Bootstrap-based chat interface.
- File uploads supported.
- Errors surface through styled alerts.
- Debug panel with logs + performance markers. 

---

## 📋 Why This Project?

Most LLM demos just send a prompt → get an answer. Real agents do more: they think, call tools, and iterate until finished.
This POC is designed to:
1. Show how that loop can run entirely client-side in JS.
2. Stay hackable and minimal so others can build on it.

### Agent Logic (Conceptual)
```python
def loop(llm):
    msg = [user_input()]
    while True:
        output, tool_calls = llm(msg, tools)
        print("Agent: ", output)
        if tool_calls:
            msg += [handle_tool_call(tc) for tc in tool_calls]
        else:
            msg.append(user_input())
````

---

## 🚀 Setup & Run

### What You’ll Need

* A modern browser (Chrome/Edge/Firefox).
* API keys for:

  * [AI Pipe](https://aipipe.org/) proxy API (recommended)
  * Optional: OpenAI, Gemini, or other providers.

### Setup

1. Clone this repo:

   ```bash
   git clone https://github.com/DevyanshJain/TDS-LLM-Agent
   cd TDS-LLM-Agent
   ```

2. Open `index.html` in your browser.
   *(No backend server required — everything runs client-side!)*

3. Configure your API key in the **Settings Panel** inside the app.

---

## 📖 Example Conversation

**User:** Interview me to create a blog post.
**Agent:** Sure! What’s the post about?

**User:** About IBM.
**Agent:** Let me search for IBM.
→ *calls `search("IBM")`*

**Agent:** IBM is a global tech company founded in 1911...

**User:** Next step, please.
**Agent:** Let’s draft an outline for your blog post...

---

## 🧪 Deliverable

* A **browser JS app** with:

  * LLM chat window
  * Google Search snippets
  * AI Pipe proxy integration
  * JS code execution sandbox

* Uses **OpenAI-style function calling**.

* Handles errors gracefully.

* Easy to extend for more tools.

---

## 📂 Project Structure

```
├── index.html   # Frontend UI (chat + settings)
├── agent.js     # Core agent loop, providers, and tools
├── styles.css     # css file
└── README.md    # Documentation (this file)
```

---

## 🙌 Acknowledgements

* [AI Pipe](https://aipipe.org/) for proxy API workflows
* OpenAI/Anthropic/Google for LLM providers
* Bootstrap for UI components

---
