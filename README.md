Bolt.new: AI-Powered Full-Stack Web Development in the Browser


This fork of Bolt.new integrates an extension built by Cole Medin that allows users to select different Large Language Models (LLMs) to write code within Bolt.new. Currently, you can choose from models like OpenAI, Anthropic, Ollama, and Groq, and it’s easily extendable to support additional models through the Vercel AI SDK. See the instructions below for running this locally and extending it to include more models.

Acknowledgment
Special thanks to Cole Medin for creating the extension that makes this flexibility possible, allowing users to switch between LLMs in real time while using Bolt.new.

What Makes Bolt.new Different
While many AI development platforms are limited to code suggestions, Bolt.new goes further, empowering users with a complete in-browser development experience:

Full-Stack in the Browser: With StackBlitz’s WebContainers, you can:

Install and run npm tools and libraries (like Vite, Next.js, etc.)
Run Node.js servers directly in your browser
Interact with third-party APIs
Deploy apps to production directly from chat
Share your projects with a live URL
AI with Environment Control: Unlike other environments where AI assists only with code generation, Bolt.new gives AI models full control over your development workspace, including the filesystem, Node.js server, terminal, and browser console. This enables a fully integrated app development experience from code creation to deployment.

Whether you're a seasoned developer or new to full-stack development, Bolt.new makes it easy to build production-ready applications with the help of AI.

Prerequisites
Ensure you have the following installed before you begin:

Node.js (v20.15.1)
pnpm (v9.4.0)
Setup
Clone the repository:
bash
Copy code
git clone https://github.com/coleam00/bolt.new-any-llm.git
Install dependencies:
bash
Copy code
pnpm install
Rename .env.example to .env.local and add your LLM API keys (only add keys for the models you intend to use; Ollama does not require an API key since it runs locally):
makefile
Copy code
GROQ_API_KEY=XXX
OPENAI_API_KEY=XXX
ANTHROPIC_API_KEY=XXX
Optionally, set the debug level:

lua
Copy code
VITE_LOG_LEVEL=debug
Important: Never commit your .env.local file to version control. It's already included in .gitignore.

Adding New LLMs:
To add new LLMs, navigate to app/utils/constants.ts and modify the MODEL_LIST constant. Each model is represented as an object with a model ID (from the provider's API documentation), a label for the frontend dropdown, and the provider’s name.

Anthropic, OpenAI, Groq, and Ollama are included by default, but the code is designed to be extendable. You can follow the tutorial in the repository’s YouTube video for detailed instructions on adding more models.

Make sure to install any Ollama models locally before using them in the app.

