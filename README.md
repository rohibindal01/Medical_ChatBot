# 📄 Project README

## 📌 Project Overview
This project is a Flask-based web application that provides a chat interface powered by a Question-Answering (QA) system. Users can input queries and receive responses generated through a backend QA chain (likely using an LLM and a vector store).

The application maintains chat history using session storage and provides a simple interface for interaction.

---

## 🔄 Basic Flow of the Project

1. User opens the web application (`/` route)
2. A session is initialized to store chat messages
3. User submits a query via form input
4. The query is:
   - Stored in session as a user message
   - Passed to a QA chain (`create_qa_chain`)
5. QA chain processes the query and returns a response
6. Response is:
   - Stored in session as assistant message
   - Displayed back to the user
7. User can:
   - Continue conversation (context preserved in session)
   - Clear chat using `/clear` route

---

## 🛠️ Technologies Used

- Backend Framework: Flask
- Templating Engine: Jinja2
- Environment Management: python-dotenv
- LLM Integration: Hugging Face (via HF_TOKEN)
- Custom Components: QA Chain (`create_qa_chain`)
- Session Management: Flask sessions
- HTML Rendering Enhancements: MarkupSafe

---

## 🏗️ Flow Architecture

```
User Input (Browser)
        ↓
Flask Route (/)
        ↓
Session Management (stores messages)
        ↓
create_qa_chain()
        ↓
LLM + Vector Store Processing
        ↓
Response Generated
        ↓
Stored in Session
        ↓
Rendered in UI (index.html)
```

---

## ▶️ How to Run the Project

1. Install dependencies:
 ```bash
 pip install flask python-dotenv

2. Set environment variables in .env:
HF_TOKEN=your_huggingface_token

3. Run the application:
python application.py

4. Open in browser:
http://localhost:5000
