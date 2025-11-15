# 🚀 The Smart Recipe Planner

> A Sequential Agent System for Recipe and Grocery Planning

### 📋 Project Overview

This project is a **Concierge Agent** for the Agents Intensive Capstone Project, built as a Kaggle Notebook. It's a simple, powerful demonstration of a multi-agent system that turns a user's meal idea into an actionable plan, from recipe to shopping list.

| | |
| :--- | :--- |
| **Project** | **The Smart Recipe Planner** |
| **Track** | **Concierge Agents** |
| **Tech Stack** | Python, Google Gemini API (`google-genai` SDK), Kaggle Notebooks |
| **Model** | `models/gemini-1.5-flash-latest` |
| **Key Features** | Sequential Agents, Built-in Tools (`GoogleSearch`), Session Management |

### 🎯 The Problem

> The process of deciding "what's for dinner" is fragmented. A user finds a recipe on one site, manually lists the ingredients in a notes app, and then opens a *third* app (like Google Maps) to find a store. This "chore chain" involves constant context-switching and is a perfect problem for an AI assistant to solve.

### 🤖 How It Works: A 2-Agent System

This system is a **sequential workflow**. The output of the first agent is the input for the second, creating a clear chain of reasoning and action.

**User Request** ➡️ **[Agent 1: `RecipeAgent`]** ➡️ **(Session State: `ingredient_list`)** ➡️ **[Agent 2: `ShoppingAgent`]** ➡️ **Final Plan**

1.  **Agent 1: The `RecipeAgent`**
    * **Task:** Receives the user's request (e.g., "simple vegetarian pasta").
    * **Action:** Uses the LLM to find one recipe and extract *only* its name and ingredients.

2.  **Agent 2: The `ShoppingAgent`**
    * **Task:** Receives the `ingredient_list` from Agent 1.
    * **Action:** Uses its built-in `GoogleSearch` tool to find a real-world grocery store near a set location.

### ▶️ How to Run This Project

This project is designed as a **Kaggle Notebook**.

1.  **Environment:** Open the `.ipynb` file in a Kaggle Notebook.
2.  **Add API Secret:**
    * In the Kaggle editor, go to **Add-ons > Secrets**.
    * Add your Google Gemini API key with the name `GOOGLE_API_KEY`. The code is set up to read this key automatically.
3.  **Run:** Simply run the cells in order from top to bottom.

### 🏆 Key Concepts Demonstrated

* **Sequential Multi-Agent System:** Agent 2 is 100% dependent on the output from Agent 1.
* **LLM-Powered Agents:** Both agents use `gemini-1.5-flash-latest` for reasoning.
* **Built-in Tools:** The `ShoppingAgent` successfully uses the `GoogleSearch` tool.
* **Session & State Management:** The `ingredient_list` variable acts as the "session state" passed between agents.

### 🔮 Future Improvements

* **Long-Term Memory:** Add a vector database to remember user preferences (diet, home address, favorite store).
* **OpenAPI Tools:** Connect to a grocery store's API to check item availability and add to a cart.
* **Expand the Agent Team:** Add a `NutritionAgent` or `ReviewAgent` to run in parallel.
