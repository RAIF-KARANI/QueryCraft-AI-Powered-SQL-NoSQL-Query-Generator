# ⚡ QueryCraft

![QueryCraft Banner](https://querycraft.hubzero.in/) 

## Overview

**QueryCraft** is an advanced, AI-driven database querying assistant that bridges the gap between natural language and complex database operations. 

Whether you are connecting to an enterprise PostgreSQL server, querying a Neo4j graph, or simply uploading a local CSV file, QueryCraft allows you to interact with your data using conversational English. The platform intelligently routes your requests to state-of-the-art Large Language Models (LLMs) to generate, explain, and execute syntactically correct queries (SQL, MongoDB shell, Cypher, etc.) in real-time.

This repository serves as the central hub and documentation entry point for the QueryCraft ecosystem. 

---

## 📂 Project Repositories

QueryCraft is divided into two main repositories to separate concerns between the user interface and the core processing API.

### 1. [QueryCraft Frontend](https://github.com/Rifaque/querycraft-frontend)
The interactive, visually immersive user interface. Built with **Next.js 15**, **React 19**, and **Tailwind CSS v4**, it features a real-time chat interface, 3D WebGL elements via Three.js, secure authentication flows, and beautiful syntax-highlighted code cards.

* **Clone:** `git clone https://github.com/Rifaque/querycraft-frontend.git`

### 2. [QueryCraft Backend](https://github.com/Rifaque/querycraft-backend)
The robust, scalable API engine. Built with **Node.js** and **Express**, it handles database connections, file-to-database conversions, JWT authentication, and intelligent routing to various LLM providers (Google GenAI, OpenRouter, and local models).

* **Clone:** `git clone https://github.com/Rifaque/querycraft-backend.git`

---

## ✨ Key Features of the Ecosystem

### 🧠 Intelligent AI Integration
* **Multi-Model Routing:** Dynamically routes natural language prompts to different LLMs based on task complexity. Uses lightweight models for simple SQL, and powerful models (like Gemini 2.5 Flash or DeepSeek R1 via OpenRouter) for complex analysis or vector searches.
* **Conversation Memory:** Maintains long-term chat context. The backend automatically summarizes older messages in the background to optimize token usage without losing user intent.
* **Resilient Parsing:** Robust regex-based extraction to separate LLM conversational text from executable database commands, ensuring only safe code blocks are executed.

### 🗄️ Universal Database Support
* **Multi-Engine Execution:** Directly supports executing generated queries against PostgreSQL, MySQL, MariaDB, MongoDB, Neo4j, and SQLite.
* **Instant File-to-Database:** Upload raw data files (CSV, JSON, SQL). The backend automatically parses and converts them into secure, temporary SQLite databases ready for instant AI querying.

### 💻 Immersive User Experience
* **Interactive Chat UI:** A seamless, responsive chat interface with typing indicators, Markdown support, and Framer Motion animations.
* **Code Visualization:** AI-generated queries are rendered in beautiful, syntax-highlighted code blocks using PrismJS.
* **3D Landing Elements:** Engaging WebGL 3D introductory visuals powered by Three.js and React Three Fiber.

---

## 🏗️ High-Level System Architecture

QueryCraft operates on a client-server model optimized for AI data processing:

1. **User Input:** The user types a natural language request (e.g., *"Show me the top 5 customers by revenue from the uploaded CSV"*) or provides a database connection string in the Next.js **Frontend**.
2. **API Layer:** The request hits the Node.js **Backend**, which validates the JWT token and fetches the user's chat history from the MongoDB state database.
3. **LLM Generation:** The backend constructs a highly constrained, guided prompt (including schema hints and chat history) and routes it to the optimal AI model (Gemini, OpenRouter, or Local).
4. **Execution:** The backend parses the LLM's response, extracts the raw SQL/NoSQL query, and executes it securely against the connected database or the temporary SQLite file instance.
5. **Presentation:** The execution results and the AI's explanation are sent back to the frontend, where they are rendered in an accessible, syntax-highlighted chat card.

---

## 🛠️ Technology Stack

| Domain | Technologies Used |
| :--- | :--- |
| **Frontend** | Next.js 15, React 19, Tailwind CSS v4, Framer Motion, Radix UI, Three.js, PrismJS |
| **Backend** | Node.js, Express.js, JWT, bcryptjs, Multer, better-sqlite3 |
| **Databases (App State)**| MongoDB, Mongoose |
| **Databases (Supported)**| PostgreSQL, MySQL, MariaDB, MongoDB, Neo4j, SQLite |
| **AI / LLMs** | Google GenAI SDK (`@google/genai`), OpenRouter API, Local Models (Ollama) |

---

## 🚀 Getting Started

To run the full QueryCraft stack locally, you will need to run both the backend and frontend simultaneously.

### Step 1: Start the Backend
1. Clone the backend repository: `git clone https://github.com/Rifaque/querycraft-backend.git`
2. Navigate to the directory: `cd querycraft-backend`
3. Install dependencies: `npm install`
4. Set up your `.env` file (requires a MongoDB instance and LLM API keys—see backend README for details).
5. Start the server: `npm run dev` (Runs on `http://localhost:5001`)

### Step 2: Start the Frontend
1. Open a new terminal window.
2. Clone the frontend repository: `git clone https://github.com/Rifaque/querycraft-frontend.git`
3. Navigate to the directory: `cd querycraft-frontend`
4. Install dependencies: `npm install`
5. Set up your `.env.local` to point to the backend: `NEXT_PUBLIC_API_URL=http://localhost:5001/api`
6. Start the client: `npm run dev` (Runs on `http://localhost:3000`)

---

## 🎯 Use Cases

* **Data Analysts:** Quickly generate complex JOINs or Aggregation pipelines without memorizing exact syntax.
* **Software Developers:** Prototype database schemas, test queries across different DB engines (SQL vs. Cypher), or interact with local CSV dumps seamlessly.
* **Non-Technical Users:** Extract insights from spreadsheets or business databases simply by asking questions in plain English.

---

## 📄 License

Both the frontend and backend of QueryCraft are licensed under the **MIT License**. See the respective repository `LICENSE` files for details.
