# 🤖 Generative AI with Gemini 1.5 Pro (Google AI Studio API)
This project demonstrates how to use Google’s Gemini 1.5 Pro model (formerly Bard/ChatGPT equivalent) via the google.generativeai Python SDK to generate creative and intelligent content using natural language prompts.

## It includes examples such as:

Text generation

Streaming responses

Safe content filtering

System instructions

Chat-based sessions with memory

## 📦 Requirements
Install the official SDK using pip:

! pip install google-generativeai
## 🔑 API Key Setup
Visit Google AI Studio to get your API key.

Replace this line in the code:

* api_key = 'Enter your API KEY'

## 🚀 Usage Examples
### 📜 Basic Text Generation

* prompt = "Write a short poem about the ocean."
* response = model.generate_content(prompt)
* print(response.text)

## 🔁 Streaming (Ideal for Long Content)

* response = model.generate_content("Write a long story about a cat.", stream=True)

* for chunk in response:
*    print(chunk.text)

## 🔒 Safety Filters
Avoid inappropriate or unsafe responses using custom safety settings:

* safety_settings = [
  {"category": "HARM_CATEGORY_HARASSMENT", "threshold": "BLOCK_MEDIUM_AND_ABOVE"},
  {"category": "HARM_CATEGORY_HATE_SPEECH", "threshold": "BLOCK_MEDIUM_AND_ABOVE"},
  {"category": "HARM_CATEGORY_SEXUALLY_EXPLICIT", "threshold": "BLOCK_MEDIUM_AND_ABOVE"},
  {"category": "HARM_CATEGORY_DANGEROUS_CONTENT", "threshold": "BLOCK_MEDIUM_AND_ABOVE"}
]

* response = model.generate_content("Tell me a joke", safety_settings=safety_settings)
* print(response.text)
## 💬 Chat Sessions (With Memory)

* chat = model.start_chat()
* chat.send_message("Hello!")
* chat.send_message("What is the capital of France?")
The chat remembers the previous message.

## ⚙️ System Instructions (Role Definition)
You can set a system instruction like this:

* chat = model.start_chat(system_instruction="You are a helpful and concise assistant.")
* response = chat.send_message("Summarize the plot of Hamlet in three sentences.")
* print(response.text)

## 🧠 About This Project
This notebook explores prompt engineering and conversational AI using Gemini 1.5 Pro, an advanced generative model by Google. It can be used for:

> Chatbots

> Story writing

> Summarization

> Educational tools

> Safe content generation

## ✍️ Author & Credits
Developed using Google Generative AI Studio & Python SDK.
Inspired by prompt engineering techniques and AI-assisted development workflows.

## 📜 License
MIT License — free to use and modify.
