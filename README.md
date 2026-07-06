# 🍽️ AI Restaurant Messenger Bot

An AI-powered restaurant chatbot built with **n8n**, **OpenAI**, **Facebook Messenger**, **Google Sheets**, and **PostgreSQL**.

The bot automatically receives customer messages from Facebook Messenger, understands customer intent, answers menu questions, processes food orders, stores data in Google Sheets, and responds instantly using AI.

---

# ✨ Features

- 🤖 AI-powered conversations using OpenAI
- 💬 Facebook Messenger integration
- 🍔 Smart food ordering
- 📋 Automatic order extraction
- ❓ Menu and restaurant inquiries
- 🧠 Conversation memory using PostgreSQL
- 📄 Save customer information to Google Sheets
- 🛒 Save ordered products to Google Sheets
- 🎤 Voice message support
- 🖼️ Image message support
- ⚡ Fully automated n8n workflow

---

# 🚀 Workflow Overview

The workflow performs the following steps:

1. Receive Messenger webhook events.
2. Detect the message type.
3. Process:
   - Text messages
   - Voice messages
   - Image messages
4. Analyze images (if provided).
5. Convert voice messages to text.
6. Send the user request to the OpenAI Assistant.
7. Classify the response into:
   - Order
   - Inquiry
   - Other
8. Store customer information.
9. Store ordered products.
10. Send the AI response back through Facebook Messenger.

---

# 🛠️ Technologies Used

- n8n
- OpenAI API
- Facebook Messenger Graph API
- Google Sheets
- PostgreSQL
- JavaScript

---

# 📂 Workflow Structure

```
Webhook
│
├── Respond to Webhook
│
├── Message Classification
│
├── Image Processing
│   ├── Download Image
│   └── Analyze Image
│
├── Voice Processing
│   ├── Download Voice
│   └── Speech To Text
│
└── AI Restaurant Assistant
      │
      ├── OpenAI
      │
      ├── JavaScript
      │
      ├── Switch
      │      ├── Order
      │      ├── Inquiry
      │      └── Other
      │
      ├── Google Sheets
      │      ├── Clients
      │      └── Products
      │
      ├── Merge
      │
      └── Messenger Response
```

---

# 📦 Google Sheets

The workflow uses two sheets:

### Clients

Stores customer information.

Fields:

- Name
- Phone
- Address

### Products

Stores ordered products.

Fields:

- Customer
- Product
- Quantity
- Unit
- Price
- Total

---

# 🔑 Required Credentials

Configure the following credentials inside n8n before running the workflow:

- OpenAI API Key
- Facebook Page Access Token
- Google Sheets OAuth2
- PostgreSQL Database

---

# ⚙️ Setup

1. Clone the repository.

```bash
git clone https://github.com/your-username/restaurant-messenger-bot.git
```

2. Import the workflow into n8n.

3. Configure all credentials.

4. Connect your Google Sheets.

5. Configure the Facebook Webhook.

6. Activate the workflow.

---

# 📌 Supported Message Types

- Text
- Voice
- Image

---

# 📋 AI Response Types

The AI always returns one of the following:

### Order

```json
{
  "type": "order",
  "customer": {},
  "items": []
}
```

### Inquiry

```json
{
  "type": "inquiry",
  "reply": ""
}
```

### Other

```json
{
  "type": "other",
  "reply": ""
}
```

---

# 📈 Future Improvements

- WhatsApp Integration
- Telegram Integration
- Online Payments
- Order Tracking
- Admin Dashboard
- CRM Integration
- Multi-language Support

---

# 📁 Repository Structure

```
restaurant-messenger-bot/
│
├── workflow/
│   └── restaurant-bot.json
│
├── README.md
│
├── LICENSE
│
└── .gitignore
```

---

# 📄 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

Ahmed Mostafa

GitHub: https://github.com/your-username
