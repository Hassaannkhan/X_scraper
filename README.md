# X.com (Twitter) Scraper with Selenium

A powerful Python-based scraper to extract posts from **X.com (formerly Twitter)** using `Selenium`, `BeautifulSoup`, and browser automation. This script allows authenticated scraping (via login) and saves extracted tweet data into a CSV file.

---

## 🚀 Features

* ✅ Logs into X.com using a real user account
* 📄 Extracts tweet text, emojis, timestamp, image link, and tweet URL
* 🔁 Scrolls dynamically to load more tweets
* 📊 Saves scraped data incrementally into a CSV file
* 📦 Easy to configure and extend

---

## 🧰 Requirements

* Python 3.7+
* Google Chrome installed
* ChromeDriver (automatically managed via `webdriver-manager`)

### 📦 Install dependencies

```bash
pip install selenium beautifulsoup4 pandas webdriver-manager
```

---

## 🛠 How It Works

1. Launches Chrome with a realistic user-agent.
2. Logs into X.com using the provided credentials.
3. Navigates to the target account or post URL.
4. Scrolls through the feed and extracts tweet details using BeautifulSoup.
5. Appends the data to a CSV file after each scroll.

---

## 📝 Data Extracted

Each tweet/post includes:

* **User name**
* **Timestamp**
* **Tweet text**
* **Extracted emojis**
* **Image link (if available)**
* **Tweet URL**
* *(Likes, Reposts, and Comments parsing is in place but commented out.)*

---

## ⚙️ Usage

### 🔐 Login Info

Set your credentials and target URL in the `__main__` section:

```python
if __name__ == "__main__":
    url = "https://x.com/DVAAus"              # Replace with the target account or post URL
    filename = "awmemorial_X_posts.csv"       # Output CSV file
    username = "your_x_username"              # Your X.com username or email
    password = "your_x_password"              # Your X.com password

    tweets = scrape_tweets(url, filename, username, password)
```

### 🛑 Notes on Login

* 2FA accounts are not supported by this script.
* Make sure your account doesn’t have login verification blocks.
* Avoid scraping too fast to prevent being rate-limited.

---

## 📁 Output Example

CSV file includes columns like:

| user\_name | timestamp            | text                   | emojis | image\_link      | tweet\_url                          |
| ---------- | -------------------- | ---------------------- | ------ | ---------------- | ----------------------------------- |
| @DVAAus    | 2025-07-01T12:34:56Z | "Honoring heroes 🇦🇺" | 🇦🇺   | `https://...jpg` | [https://x.com/](https://x.com/)... |

---

## 🧠 Limitations

* Likes, Reposts, and Comments are not scraped by default due to dynamic nature (code is present but commented out).
* X.com may change its layout or block automated logins.
* Requires login (cannot scrape anonymously).

---

## 📌 Tips

* Run the script in a visible (non-headless) Chrome for better reliability.
* Adjust scroll time or count if content is loading slowly.
* Consider using proxies or VPNs if you face geo-blocking.

---

## ⚠️ Disclaimer

> **This script is intended for research and educational purposes only.**
>
> Scraping X.com may violate their [Terms of Service](https://x.com/en/tos). Use at your own risk. The authors take no responsibility for misuse.
