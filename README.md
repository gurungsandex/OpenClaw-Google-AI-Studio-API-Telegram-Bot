# OpenClaw + Google AI Studio API + Telegram Bot Integration

This guide continues from my previous repo/article where I installed OpenClaw on an Azure VM using Ollama.

If you haven’t checked that setup yet, please review the previous repository/article first. 

In this version, instead of using a local LLM (Ollama), I’m connecting OpenClaw to:
* Google AI Studio (Free API Key)
* Telegram Bot 

This makes the setup more practical because now your AI assistant lives inside Telegram.

---

# Prerequisites

Before starting, make sure you:
* Have an Azure VM running Ubuntu (from previous guide)
* Have OpenClaw already installed
* Can access your VM via SSH or Bastion
* Have a Google account
* Have Telegram installed

If not, follow the previous article for VM hosting and OpenClaw installation.

---

# Step 1 – Generate Google AI Studio API Key
1. Go to **Google AI Studio**
2. Sign in with your Google account
3. Navigate to **API Keys**
4. Click **Generate API Key**
5. Copy and save the key securely
<img width="856" height="488" alt="Screenshot 2026-02-27 at 4 22 54 PM" src="https://github.com/user-attachments/assets/eadfa95e-b392-489c-8619-0790b4fd85c4" />

---

# Step 2 – Configure OpenClaw with Google AI
Please review my previous repository/article to check OpenClaw installation on Azure Virtual machine. 

Now go back to your OpenClaw settings inside the VM.
When configuring the AI provider:
* Select **Google** as the Authentication Provider
* Select **Google Auth** method
* Paste the API key you generated earlier
<img width="687" height="453" alt="Screenshot 2026-02-27 at 4 24 29 PM" src="https://github.com/user-attachments/assets/e6119361-bc21-4167-b827-3ecc00216bcf" />


For the model selection:
* Choose `google/gemini-2` or a higher available model
  (Gemini 1.5 may be retired depending on availability)
<img width="726" height="626" alt="Screenshot 2026-02-27 at 4 25 28 PM" src="https://github.com/user-attachments/assets/5fef6100-43db-4bc2-8a68-dcb2abf4bdc3" />

Save the configuration.
At this point, OpenClaw is connected to Google’s Gemini model.

---

# Step 3 – Create a Telegram Bot

Now we’ll connect OpenClaw to Telegram.
1. Open Telegram
2. Search for **BotFather**
3. Start a chat
4. Type:

```
/newbot
```

BotFather will guide you through:
* Giving your bot a name
* Creating a unique username

After that, Telegram will generate a **Bot API Token**.
Copy this token — you’ll need it in OpenClaw.
<img width="619" height="687" alt="Screenshot 2026-02-27 at 4 27 13 PM" src="https://github.com/user-attachments/assets/9aed666e-b172-4266-a6c4-9c856ac8c2ae" />

---

# Step 4 – Pair Telegram with OpenClaw
Type this in Telegram to get the pairing code.
```
/start
```

Once you receive the pairing code, run this command inside your VM:
```bash
openclaw pairing approve telegram <YOUR_PAIRING_CODE>
```
Replace `<YOUR_PAIRING_CODE>` with the actual code provided in Telegram. 

If successful, your Telegram bot is now connected to OpenClaw.
<img width="824" height="253" alt="Screenshot 2026-02-27 at 4 26 16 PM" src="https://github.com/user-attachments/assets/cb999e97-86d4-428c-bbeb-5619e4e8ab81" />

---

# Step 5 – Test the Telegram AI Bot

Now open Telegram and message your newly created bot.

You should see responses powered by:
* Google Gemini model
* OpenClaw backend
* Your Azure VM

<img width="463" height="829" alt="Screenshot 2026-02-27 at 4 33 16 PM" src="https://github.com/user-attachments/assets/9c418dcb-48b0-49a2-91af-35f24b70544c" />

You can now chat with your AI assistant directly from Telegram.

---

# What You Can Do With This Setup

With OpenClaw connected to Telegram and Gemini, you can:
* Chat with your AI assistant
* Manage files (if configured)
* Automate tasks
* Browse the web
* Trigger workflows
* Control system actions (with proper permissions)

⚠️ Important:
To manage files, automate tasks, browse the web, or control your computer, you must properly configure your self-hosted environment. This setup acts as a bridge between Telegram and your system hardware.

Be mindful of permissions and security when enabling advanced features.

---

# Why This Lab Is Valuable

This setup demonstrates:
* Cloud-hosted AI infrastructure (Azure VM)
* API integration (Google AI Studio)
* Secure key management
* Messaging platform integration (Telegram)
* Automation-ready AI deployment
* Real-world LLM implementation

This is no longer just a local lab — it’s an interactive AI system accessible from your phone.

---

# Final Thoughts

In this continuation lab, we moved from Local LLM (Ollama) ➜ Cloud AI API (Google Gemini) ➜ Telegram Integration

This setup is:
* Free to start
* Practical
* Expandable
* Portfolio-ready



Enjoy your learning 
