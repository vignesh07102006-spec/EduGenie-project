# EduGenie-project
🎓 EduGenie

Your AI-powered learning companion — ask questions, get clear explanations, and learn smarter.

EduGenie is an AI-powered educational assistant built with FastAPI and Google Gemini. It provides a simple, responsive interface where students can ask questions and receive AI-generated answers and explanations.

✨ Features

🤖 AI-Powered Q&A — Ask educational questions and get intelligent answers.

📚 Student-Friendly Explanations — Designed to make complex concepts easier to understand.

⚡ FastAPI Backend — Lightweight and high-performance API architecture.

🧠 Google Gemini Integration — Uses Gemini models for AI-generated responses.

🌐 Simple Web Interface — Clean frontend built with HTML, CSS, and JavaScript.

❤️ Health Monitoring — Built-in /health endpoint for checking service status.

🔄 Development Reloading — Uvicorn hot reload for faster development.

⚙️ Environment-Based Configuration — API keys and settings are managed through .env.

🧩 Modular Architecture — AI functionality is separated from the API layer for easier maintenance.

🖥️ Preview
EduGenie — AI Learning Assistant
┌─────────────────────────────────────────────────────┐
│                    🎓 EduGenie                      │
│              Your AI Learning Companion             │
├─────────────────────────────────────────────────────┤
│                                                     │
│  Ask anything you want to learn...                  │
│                                                     │
│  ┌───────────────────────────────────────────────┐  │
│  │ Which is the largest ocean?              🔍 │  │
│  └───────────────────────────────────────────────┘  │
│                                                     │
│                    Ask EduGenie                    │
│                                                     │
│  💡 Answer                                           │
│  The Pacific Ocean is the largest ocean on Earth.  │
│                                                     │
└─────────────────────────────────────────────────────┘

🏗️ Architecture
                    ┌─────────────────┐
                    │     Student     │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   Web Frontend  │
                    │ HTML/CSS/JS     │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │    FastAPI      │
                    │     Backend     │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ EduGenie AI     │
                    │    Module       │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │  Google Gemini  │
                    │      API        │
                    └─────────────────┘

📁 Project Structure
EduGenie/
│
├── .venv/                  # Python virtual environment
├── .env                    # Environment variables
├── .gitignore              # Git ignore rules
│
├── main.py                 # FastAPI application
│
├── edugenie/
│   └── gemini.py           # Gemini AI integration
│
├── static/
│   ├── style.css           # Frontend styling
│   └── app.js              # Frontend JavaScript
│
├── templates/
│   └── index.html           # Main web page
│
└── README.md


Your exact folder structure may differ depending on the current version of the project.

🚀 Getting Started
1. Clone the Repository
git clone <YOUR_REPOSITORY_URL>
cd EduGenie

2. Create a Virtual Environment
Windows
python -m venv .venv


Activate it:

.venv\Scripts\activate


You should see:

(.venv)


at the beginning of your terminal prompt.

3. Install Dependencies

If the project contains requirements.txt:

pip install -r requirements.txt


Otherwise, install the required packages:

pip install fastapi uvicorn google-genai python-dotenv

4. Configure the Environment

Create a file named:

.env


in the project root.

Example:

GEMINI_API_KEY=YOUR_GEMINI_API_KEY
GEMINI_MODEL=gemini-3.5-flash-lite
EXPLAIN_BACKEND=local
LOCAL_MODEL_NAME=MBZUAI/LaMini-Flan-T5-783M
MAX_INPUT_CHARS=12000

🔐 Important

Never commit your .env file.

Add this to .gitignore:

.env
.venv/
__pycache__/
*.pyc

🔑 Getting a Gemini API Key

Create your API key through Google AI Studio.

After creating the key, put it in:

GEMINI_API_KEY=YOUR_KEY_HERE


Do not hard-code your API key inside Python files.

▶️ Run EduGenie

From the project directory:

uvicorn main:app --reload


You should see:

Uvicorn running on http://127.0.0.1:8000


Open your browser:

http://127.0.0.1:8000


🎉 EduGenie is now running locally.

🔌 API Endpoints
Health Check
GET /health


Example:

http://127.0.0.1:8000/health


Used to verify that the application is running.

Ask a Question
GET /qa?question=YOUR_QUESTION


Example:

http://127.0.0.1:8000/qa?question=Which%20is%20the%20largest%20ocean?


Example response:

{
  "answer": "The Pacific Ocean is the largest ocean on Earth."
}

🧠 AI Model

EduGenie uses Google's Gemini API for generating educational responses.

The model can be configured through:

GEMINI_MODEL=gemini-3.5-flash-lite


This makes it possible to change models without modifying the application code.

⚙️ Configuration

EduGenie supports environment-based configuration.

Variable	Purpose
GEMINI_API_KEY	Google Gemini API key
GEMINI_MODEL	Gemini model used for responses
EXPLAIN_BACKEND	Explanation backend
LOCAL_MODEL_NAME	Optional local Hugging Face model
MAX_INPUT_CHARS	Maximum input size

Example:

GEMINI_API_KEY=YOUR_KEY
GEMINI_MODEL=gemini-3.5-flash-lite
EXPLAIN_BACKEND=local
LOCAL_MODEL_NAME=MBZUAI/LaMini-Flan-T5-783M
MAX_INPUT_CHARS=12000

🛠️ Development

Start the development server:

uvicorn main:app --reload


The --reload option automatically restarts the server when Python files change.

Useful URLs:

Application
http://127.0.0.1:8000

Health
http://127.0.0.1:8000/health

API Documentation
http://127.0.0.1:8000/docs

Alternative API Documentation
http://127.0.0.1:8000/redoc

🧪 Example Questions

Try asking EduGenie:

What is photosynthesis?

Explain Newton's first law.

What is the largest ocean?

Why does the Earth rotate?

Explain recursion in simple terms.

What is the difference between RAM and ROM?

Explain the water cycle.

🔒 Security

EduGenie uses environment variables to protect sensitive configuration.

Never do this:
GEMINI_API_KEY = "AIza..."

Instead:
import os

api_key = os.getenv("GEMINI_API_KEY")


And store the key in:

.env


Make sure .env is included in .gitignore.

⚠️ If an API key is accidentally exposed publicly, revoke it immediately and create a replacement key.

🧰 Tech Stack
Technology	Purpose
🐍 Python	Core programming language
⚡ FastAPI	Backend API
🚀 Uvicorn	ASGI server
🤖 Google Gemini	AI generation
🌐 HTML	Frontend structure
🎨 CSS	Frontend styling
⚙️ JavaScript	Frontend interaction
🔐 python-dotenv	Environment configuration
🧠 Hugging Face	Optional local explanation model
🗺️ Roadmap

EduGenie can be expanded with features such as:

 💬 Conversation history

 👤 User accounts

 📚 Subject-specific AI tutors

 📝 AI-generated quizzes

 🧠 Personalized learning paths

 📊 Student progress tracking

 📄 PDF/document-based Q&A

 🔊 Text-to-speech answers

 🌎 Multi-language support

 📱 Mobile-friendly interface

 🌙 Dark mode

 🧪 Automated tests

 🚀 Production deployment

🤝 Contributing

Contributions are welcome!

Fork the repository.

Create a feature branch.

git checkout -b feature/amazing-feature


Make your changes.

Commit your changes.

git commit -m "Add amazing feature"


Push the branch.

git push origin feature/amazing-feature


Open a Pull Request.

📜 License

This project is intended for educational and development purposes.

Add your preferred license here, such as MIT License, if you want to make the repository open-source under those terms.

👨‍💻 Author

EduGenie

Built with ❤️ using Python, FastAPI, and Google Gemini.

⭐ Support the Project

If you find EduGenie useful:

⭐ Star the repository
🍴 Fork the project
🐛 Report bugs
💡 Suggest features
🤝 Contribute improvements

🎓 EduGenie — Learn anything. Understand everything.
