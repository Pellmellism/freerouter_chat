# ✨ Freerouter Chat ✨

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**A dead-simple, single-file, browser-based chat interface for interacting with OpenRouter's free, large-context, vision-capable AI models.**

No server needed, no build steps, no complex setup. Just download the HTML file, open it, add your API key, and start chatting with powerful AI models for free!

**(Live Demo:** [**https://pellmellism.github.io/freerouter_chat/**](https://pellmellism.github.io/freerouter_chat/) **)**

---

<!-- **IMPORTANT:** Replace this placeholder with an actual screenshot or GIF! -->
![Freerouter Chat Screenshot](https://pellmellism.github.io/freerouter_chat/freerouter_chat.png)
*(Screenshot showing the chat interface with user/AI messages and model selection)*

---

## 🤔 Why Freerouter Chat?

OpenRouter offers access to a vast array of AI models, including several powerful ones available completely free (with daily limits). Freerouter Chat aims to be the simplest possible way to:

*   🚀 **Instantly Use Free Models:** Filters specifically for free models with vision capabilities and large context windows (>96k tokens).
*   🧠 **Leverage Power:** Chat with models that can understand images and handle long conversations, without paying inference costs (within limits).
*   🖱️ **Zero Setup:** It's a single HTML file. Download, open in your browser, and you're ready.
*   🔒 **Client-Side Only:** Your API key and chat history stay entirely within *your* browser (API key in a cookie, history in local storage). No data is sent to any server except OpenRouter's API itself.

## ✅ Key Features

*   📄 **Single File Application:** Everything is contained in `freerouter_chat.html`.
*   🆓 **Focus on Free Models:** Automatically fetches and filters for `:free`, vision-capable, large-context models on OpenRouter.
*   📈 **Dynamic Model List:** Models are sorted by context size (smallest first). If a model hits its daily rate limit (429 error), it's temporarily removed from the selection for the session.
*   💬 **Standard Chat Interface:** Clean, familiar chat UI similar to popular chatbots.
*   🖼️ **Image Uploads:** Attach images to your prompts (resized client-side to 512x512 and sent as Base64).
*   🕒 **Timestamps & Model Info:** Messages are timestamped, and AI responses indicate the specific model used.
*   📝 **Message Editing & Deletion:** Correct mistakes or remove messages from the history.
*   🔄 **Model Switching:** Change the active AI model mid-conversation.
*   💾 **Chat Persistence:** Chat history is saved in your browser's local storage.
*   📤 **Import/Export:** Save your chat history as a JSON file or load a previous conversation.
*   🔑 **API Key Management:** Securely prompts for your OpenRouter key and stores it in a browser cookie. Easy logout clears the key and history.
*   ✨ **Simple & Clean UI:** Built with Vue.js (via CDN) for a reactive experience without requiring a build process.

## 🛠️ Technology Stack

*   **HTML5**
*   **CSS3**
*   **JavaScript (ES6+)**
*   **Vue.js 3** (via CDN)

## 🚀 Getting Started (It's *really* simple!)

1.  **Download:** Get the `freerouter_chat.html` file from this repository.
2.  **Open:** Double-click the file to open it in your modern web browser (like Chrome, Firefox, Edge, Safari).
3.  **API Key:** The application will prompt you to enter your [OpenRouter API Key](https://openrouter.ai/keys). Paste your key and click "Save Key".
    *   > **⚠️ Security Note:** Your API key is stored in a browser cookie for convenience. This is reasonably secure for personal use on a trusted device, but avoid using it on public or shared computers.
4.  **Chat!** Select an available model from the dropdown and start sending messages or uploading images.

## ⚙️ How It Works

*   **Model Fetching:** On load (after the API key is provided), it calls the OpenRouter `/models` endpoint.
*   **Filtering:** It filters the results based on:
    *   Model ID containing `:free`.
    *   Context length >= 96,000 tokens.
    *   Model name, description, or ID containing "vision" (case-insensitive).
    *   Excludes models temporarily marked as rate-limited during the session.
*   **Sorting:** Filtered models are sorted by `context_length` ascending (uses smaller context free models first).
*   **API Calls:** Uses the standard OpenRouter `/chat/completions` endpoint directly from the browser via the `fetch` API.
*   **Image Processing:** When you upload an image, it's resized client-side to fit within a 512x512 square (maintaining aspect ratio) and converted to a Base64 JPEG string before being included in the API request.
*   **State Management:** Vue.js handles the UI reactivity, while the API key is stored in a cookie and chat history/model selection are persisted in `localStorage`.

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improvements or find a bug, please feel free to:

1.  Open an issue to discuss the change.
2.  Fork the repository and submit a pull request.

## 📄 License

Distributed under the MIT License. See the `LICENSE` file (or the license badge link) for more information.

---

*Happy (Free) Chatting!*
