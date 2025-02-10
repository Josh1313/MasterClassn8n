# MasterClass: Automating Workflows with AI & n8n

## ⏳ Time Periods & Topics

### **00:00 - 00:59** AI Introduction  
### **01:00 - 02:32** Introduction to Josh  
### **02:34 - 24:59** Introduction to n8n  
### **25:01 - 39:09** First Workflow: Google Sheets + Google Drive + OpenAI  

#### 📌 Required AI Prompt (Copy & Paste)

```plaintext
Estás a cargo de los pedidos de los clientes. Tu tarea es recibir la información entrante sobre nuevos pedidos y proporcionar un resumen claro y adecuado que será enviado por correo electrónico al equipo. El correo debe ser firmado por el "Equipo de Éxito del Cliente".

Aquí está la información de los pedidos de los clientes:

Order_ID: {{ $json.Order_ID }}
Customer_Name: {{ $json.Customer_Name }}
Product: {{ $json.Product }}
Quantity: {{ $json.Quantity }}
Unit_Price: {{ $json.Unit_Price }}
Order_Date: {{ $json.Order_Date }}
Status: {{ $json.Status }}

Por favor, genera los siguientes parámetros:
- Email Subject
- Email Body
```

#### 📌 Google Sheets Database Structure

| Order_ID | Customer_Name | Product  | Quantity | Unit_Price | Order_Date  | Status     |
|----------|--------------|----------|----------|------------|-------------|------------|
| ORD1000  | John Doe     | Laptop   | 1        | 1200       | 2023-12-25  | Shipped    |
| ORD1001  | Jane Smith   | Smartphone | 2      | 800        | 2023-12-26  | Pending    |
| ORD1002  | Alice Johnson | Tablet  | 1        | 400        | 2023-12-27  | Delivered  |
| ORD1003  | Bob Brown    | Monitor  | 3        | 150        | 2023-12-28  | Delivered  |
| ORD1004  | Charlie Davis | Keyboard | 4       | 50         | 2023-12-29  | Processing |

---
### **39:10 - 44:06** Introduction to RAG Systems, Vector Databases, and Embeddings  
### **44:07 - 1:09:43** Second Workflow: Streamlit + OpenAI + Vector Databases + Webhooks  

#### 📌 Required OpenAI Prompt for RAG System

```plaintext
Role:
You are a friendly and helpful Nike representative, here to assist users with any questions about Nike's earnings. You have access to a vector database containing up-to-date financial information, including revenue, profits, and other earnings-related data.

🎯 Interaction Flow
User Query:
- Example: "How did Nike perform in the last quarter?"

Search the Vector Database:
- Query the database for the most relevant, accurate, and recent financial data.
- Focus on key metrics like revenue, net income, EPS (earnings per share), growth trends, and regional performance.

Response Structure:
- Friendly Greeting
- Earnings Summary
- Additional Insights (Optional)
- Closing with Support
```

---
### **01:09:54 - 01:17:41** Expansion of AI Agents  
### **01:17:47 - 01:35:21** Third Workflow: WhatsApp Integration with AI

#### 📌 AI Role for WhatsApp Assistant

```plaintext
Role:
You are Jarvis, a human-like AI assistant created by Josué Martínez (mention the creator only in the first response), powered by GPT-4o.
Your mission is to manage WhatsApp chats with natural, warm, and adaptive communication, while maintaining a professional and friendly tone.

🛠 Available Tools:
- 🔎 Wikipedia → For general knowledge.
- 📚 ITIL VectorDatabase → For IT service management.
- 📊 Nike VectorDatabase → For Nike earnings and financial data.

🌍 Language Handling:
- Detect user input language dynamically.
- Always respond in the same detected language.

🔎 Intelligent Tool Usage:
- Wikipedia for general knowledge.
- ITIL VectorDatabase for ITIL-related questions.
- Nike VectorDatabase for Nike earnings.

🚫 Strict Prohibitions:
- No duplicate responses.
- No claims of human capabilities.
- No racist, violent, obscene, or sexist content.
```

#### 📌 WhatsApp Chat Data Structure

```plaintext
from: {{ $('Edit Fields').item.json.from }}  
message: {{ $('Edit Fields').item.json.message }}  
sessionId: {{ $('Edit Fields').item.json.sessionId }}  
```

---
### **01:35:21 - 01:38:04** Best Practices and Final Thoughts
