# sauce-robot

sauce-robot is an automated, event-driven Reddit bot built in Python that automatically reverse-searches images from subreddit submissions using the SauceNAO API to provide instant, reliable source attribution.

The bot monitors specified target subreddits in real-time, extracts visual image assets from new posts, cross-references them via upstream image index databases, and posts formatted credit comments automatically—drastically reducing manual moderation overhead and ensuring copyright transparency.

---

## Core Features & Engineering Focus

* **Real-Time Stream Monitoring:** Utilizes asynchronous pooling or streaming architectures to immediately intercept and evaluate incoming image submissions.
* **API Integration Pipeline:** Interacts seamlessly with the SauceNAO API, parsing complex multi-result JSON payloads to extract similarity indexes, creator links, and material origins.
* **Robust Error & Rate-Limit Handling:** Implements comprehensive backoff algorithms and defensive exception handling to respect API limits and protect against network drops.
* **Granular Filtering Logic:** Filters out low-confidence results using customizable similarity threshold settings to prevent false positives and irrelevant match comments.
* **Structured Markdown Generation:** Dynamically builds clean, readable Reddit markdown comments featuring hyperlinked source platforms and accurate percentage matching data.

---

## Installation & Deployment

### Prerequisites
* Python 3.10+
* A Reddit Developer Application account (for Client ID and Secret credentials)
* A valid SauceNAO API key profile

### Local Quickstart

1. **Clone the Repository:**
   ```bash
   git clone https://github.com
   cd sauce-robot
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure Environment Variables:**
   Create a `.env` file in the root directory based on the `.env.example` profile:
   ```env
   REDDIT_CLIENT_ID=your_client_id
   REDDIT_CLIENT_SECRET=your_client_secret
   REDDIT_USERNAME=your_bot_username
   REDDIT_PASSWORD=your_bot_password
   SAUCENAO_API_KEY=your_saucenao_api_key
   ```

4. **Execute the Automation:**
   ```bash
   python src/bot.py
   ```

---

## Security & Token Isolation Notice

> Warning: All authentication keys, account passwords, and private API profiles are kept strictly isolated outside the code baseline. A local configuration architecture via environment variables (.env) is mandatory. Never commit the final .env file to version control.
