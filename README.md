# Usman A Majid Academy 🌍

Welcome to the official repository of **Usman A Majid Academy** – a personal academic website created to share knowledge, educational content, blog posts, and more.

## 🌟 Website Link

➡️ [Visit the Website](https://usmanabdulmajid67.github.io/Usman-abdulmajid/)

## 📚 About the Academy

The Usman A Majid Academy is built to:
- Share tutorials, blogs, and resources
- Showcase academic and personal achievements
-
<nav style="background-color: #0056b3; padding: 15px;">
  <a href="index.html" style="color: white; margin-right: 20px; text-decoration: none;">Home</a>
  <a href="about.html" style="color: white; margin-right: 20px; text-decoration: none;">About</a>
  <a href="blog.html" style="color: white; margin-right: 20px; text-decoration: none;">Blog</a>
  <a href="contact.html" style="color: white; text-decoration: none;">Contact</a>
</nav>
// ask-usman-backend/index.js const express = require('express'); const cors = require('cors'); const bodyParser = require('body-parser'); const { Configuration, OpenAIApi } = require('openai');

require('dotenv').config();

const app = express(); const port = process.env.PORT || 3000;

app.use(cors()); app.use(bodyParser.json());

const configuration = new Configuration({ apiKey: process.env.OPENAI_API_KEY, }); const openai = new OpenAIApi(configuration);

app.post('/api/ask', async (req, res) => { const { question } = req.body;

try { const response = await openai.createChatCompletion({ model: 'gpt-4', messages: [ { role: 'system', content: 'You are Ask Usman, an academic assistant for secondary and junior students. Explain topics clearly, and use examples if needed.' }, { role: 'user', content: question }, ], max_tokens: 300, });

const answer = response.data.choices[0].message.content;
res.json({ answer });

} catch (error) { console.error('OpenAI API error:', error); res.status(500).json({ answer: 'Sorry, something went wrong. Please try again later.' }); } });

app.listen(port, () => { console.log(Ask Usman server running on http://localhost:${port}); });
📚 OneWorld Institute – AI-Powered Learning Platform

Welcome to the OneWorld Institute — a global virtual academy offering online tutorials and university-style education for secondary and junior students. This repository contains the backend code for Ask Usman, an AI-powered chatbot assistant that helps learners understand concepts, answer questions, and grow their academic confidence.


---

💡 Features

🌍 Online tutorial and virtual university

🤖 AI-powered assistant using OpenAI GPT

🎓 Designed for secondary and junior students

📲 Simple JSON API for chat-based learning support

🛡️ Secure with environment variables for API keys



---

🛠️ Technologies Used

Node.js

Express.js

OpenAI API (GPT-4)

CORS, Body-Parser

Render for deployment



---

🚀 How to Run Locally

1. Clone the repo:

git clone https://github.com/usmanabdulmajid67/ask-usman-backend.git
cd ask-usman-backend


2. Install dependencies:

npm install


3. Create .env file:

OPENAI_API_KEY=your-openai-api-key


4. Start the server:

node index.js



The API will be available at: http://localhost:3000/api/ask


---

🔗 API Endpoint

POST /api/ask

Request body:

{
  "question": "What is photosynthesis?"
}

Response:

{
  "answer": "Photosynthesis is the process by which green plants..."
}



---

📦 Deployment

This backend is deployed on Render, where it runs continuously and securely serves AI-based answers to students visiting the OneWorld Institute website.


---

📬 Contact

For inquiries, suggestions, or collaboration:

Email: usmanabdulmajid67@gmail.com
Website: OneWorld Institute
GitHub: @usmanabdulmajid67



