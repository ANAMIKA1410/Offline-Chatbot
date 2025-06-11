# 🧠 Offline-Chatbot

**Offline-Chatbot** is a fully offline, browser-based AI chatbot interface powered by WebLLM and WebGPU. It allows users to interact with local language models directly in the browser without requiring any server or internet connection after initial setup.

---

## 🚀 Features

- **Offline AI Chat**: Runs entirely in the browser with no server or internet required.
- **Model Selection**: Choose from multiple local models like TinyLlama, Gemma, and Phi-3.
- **WebGPU Acceleration**: Utilizes GPU for faster inference (Chrome recommended).
- **Cache-Augmented Generation (CAG)**: Load static datasets (e.g., FAQs, documents) to guide model responses.
- **Responsive UI**: Clean, modern interface with chat bubbles, avatars, and streaming responses.
- **Progress Feedback**: Real-time loading progress and status updates.
- **Auto-resizing Input**: Chat input adjusts height dynamically for better UX.

---

## 🛠️ Technologies Used

- **HTML/CSS/JavaScript**: Core frontend technologies.
- **WebLLM**: For running LLMs in-browser via [@mlc-ai/web-llm](https://github.com/mlc-ai/web-llm).
- **WebGPU**: For hardware acceleration (enable via `chrome://flags`).
- **LocalStorage (optional)**: For storing conversation history or datasets (not implemented yet).

---

## 📦 Supported Models

These models are loaded dynamically via WebLLM:

- `TinyLlama-1.1B-Chat-v1.0-q4f16_1-MLC` (~650MB, fastest)
- `gemma-2b-it-q4f16_1-MLC` (~1.4GB, fast)
- `Phi-3-mini-4k-instruct-q4f16_1-MLC` (~2.1GB, medium)

> **Note**: Larger models require more RAM (8GB+ recommended).

---

## 🧩 How It Works

1. **Model Selection**: User selects a model from the dropdown.
2. **Model Loading**: WebLLM loads the model with progress feedback.
3. **Chat Interface**: Once loaded, the chat UI is activated.
4. **CAG Dataset (Optional)**: Users can paste static data to guide responses.
5. **Message Handling**:
   - Messages are added to the conversation history.
   - If CAG is active, a system prompt is prepended.
   - Responses are streamed and rendered in real-time.

---

## 📋 CAG (Cache-Augmented Generation)

### Purpose:
Preload static content (e.g., FAQs, document excerpts) into the model's context to improve relevance.

### Usage:
- Paste content into the CAG input box.
- Click **Load Dataset**.
- The model will prioritize this content when answering.

### Notes:
- Keep datasets concise to avoid context overflow.
- You can clear or reload datasets anytime.

---

## 🖥️ Setup Instructions

1. **Enable WebGPU**:
   - Open Chrome.
   - Go to `chrome://flags`.
   - Enable **WebGPU**.
   - Restart browser.

2. **Open the Project**:
   - Clone or download this repository.
   - Open `cagBotOffline.html` in a WebGPU-enabled browser.

3. **Start Chatting**:
   - Select a model.
   - Wait for it to load.
   - Start chatting!

---

## 📌 Limitations

- Requires modern browser with WebGPU support.
- Initial model download may need internet (cached afterward).
- No persistent storage (yet).
- Limited context window (~4k tokens max).

---


