# ⚡ Instant Indexer — Free Google URL Indexing Tool

<div align="center">

[![Live Demo](https://img.shields.io/badge/🌐_Live_Demo-tanzidaltuhin.pro-F06334?style=for-the-badge)](https://tanzidaltuhin.pro/instant-indexer/)
[![License: MIT](https://img.shields.io/badge/License-MIT-00e5a0?style=for-the-badge)](LICENSE)
[![Pure HTML](https://img.shields.io/badge/Pure-HTML%20%2F%20No%20Backend-ffc94a?style=for-the-badge)]()
[![Google Indexing API](https://img.shields.io/badge/Google_Indexing-API_v3-4285F4?style=for-the-badge&logo=google)]()

**A free, browser-based dashboard to submit URLs to Google Search instantly using the official Google Indexing API v3.**

[🚀 Use the Tool](https://tanzidaltuhin.pro/instant-indexer/) · [⭐ Star this Repo](#) · [🐛 Report Bug](#issues) · [💡 Request Feature](#issues)

</div>

---

## 📖 Table of Contents

- [What is Instant Indexer?](#-what-is-instant-indexer)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Setup Guide](#-setup-guide-step-by-step)
- [How to Use the Tool](#-how-to-use-the-tool)
- [SEO & AIEO Optimization](#-seo--aieo--geo-optimization-notes)
- [FAQ](#-faq)
- [Tech Stack](#-tech-stack)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🔍 What is Instant Indexer?

**Instant Indexer** is a 100% client-side, no-backend HTML tool that uses the **Google Indexing API v3** to submit, re-index, or remove URLs from Google Search — instantly.

Instead of waiting days for Google to naturally discover your pages, this tool lets you push URLs directly into Google's crawl queue in seconds. Perfect for bloggers, SEOs, site owners, and developers who publish content frequently.

> ✅ No server. No registration. No data leaves your browser.

---

## ✨ Features

| Feature | Description |
|---|---|
| ⚡ **Instant URL Submission** | Submit URLs directly to Google's crawl queue via Indexing API |
| 🔑 **Multi-Key JSON Manager** | Upload and manage multiple Google service account keys |
| 🔄 **Auto Key Rotation** | Automatically rotates keys to maximize daily quota |
| 📊 **Daily Quota Tracking** | Visual quota bars per key, resets at midnight |
| 📋 **Bulk URL Support** | Paste 1–1000+ URLs at once, processed one by one |
| 📡 **Live Submission Log** | Real-time status (✅ success / ❌ error) per URL |
| 🗂️ **History** | Persistent local history of all past submissions |
| 🔒 **100% Client-Side** | Web Crypto API for JWT — keys never leave your device |
| 📱 **Responsive Design** | Works on mobile, tablet, and desktop |
| ♿ **Accessible** | ARIA roles, labels, keyboard navigation support |

---

## ⚙️ How It Works

```
Your Browser
    │
    ├─ Reads service account JSON key (private_key + client_email)
    ├─ Creates a JWT (RS256) using Web Crypto API
    ├─ Exchanges JWT for OAuth 2.0 access token via Google
    └─ POSTs each URL to:
         https://indexing.googleapis.com/v3/urlNotifications:publish
```

Everything happens **entirely in your browser**. No proxy, no server, no middleman.

---

## 🚀 Setup Guide (Step by Step)

### Step 1 — Create a Google Cloud Project

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Click **New Project** → give it a name → Create
3. Select your project from the top dropdown

### Step 2 — Enable the Indexing API

1. Go to **APIs & Services** → **Library**
2. Search for **"Indexing API"**
3. Click → **Enable**

### Step 3 — Create a Service Account

1. Go to **IAM & Admin** → **Service Accounts**
2. Click **+ Create Service Account**
3. Name it (e.g., `instant-indexer`) → Create & Continue
4. Skip role assignment → Done

### Step 4 — Generate JSON Key

1. Click on your service account
2. Go to **Keys** tab → **Add Key** → **Create new key**
3. Choose **JSON** → Create → Download the `.json` file

### Step 5 — Add to Google Search Console

1. Open [Google Search Console](https://search.google.com/search-console/)
2. Select your property
3. Go to **Settings** → **Users and permissions** → **Add user**
4. Enter the **client_email** from your JSON file
5. Set permission to **Owner**
6. Click **Add**

> ⚠️ This step is critical. Without it, the API will return a 403 error.

---

## 🛠️ How to Use the Tool

1. **Open** [https://tanzidaltuhin.pro/instant-indexer/](https://tanzidaltuhin.pro/instant-indexer/)
2. **Upload** your service account `.json` key file in the Key Manager panel
3. **Paste** your URLs in the URL input (one per line)
4. **Select** action:
   - `URL_UPDATED` — Request indexing or re-indexing
   - `URL_DELETED` — Request removal from Google index
5. **Click** ⚡ Submit All URLs
6. Watch the **Live Log** for real-time results

### 💡 Tips

- Each key supports **200 URLs/day**. Add multiple keys for higher throughput.
- Enable **Auto Key Rotation** to let the tool pick the best key automatically.
- History is saved in `localStorage` — it persists across sessions.
- The quota counter resets daily at midnight (based on your local time).

---

## 📈 SEO / AIEO / GEO Optimization Notes

This tool's HTML is fully optimized for:

### ✅ Traditional SEO
- Semantic HTML5 with proper `<header>`, `<main>`, `<article>`, `<footer>`, `<section>`
- Optimized `<title>`, `<meta description>`, canonical URL
- Internal keyword targeting: *google indexing api tool, instant url indexer, submit url to google*
- Human-readable SEO content section with H2, H3, H4 hierarchy
- Image meta tags for social sharing (Open Graph + Twitter Card)

### ✅ AIEO (AI Engine Optimization)
For AI-powered search engines (ChatGPT, Perplexity, Claude, Gemini):
- **FAQPage** schema markup — increases chance of being cited as an AI answer source
- **HowTo** schema — step-by-step instructions in structured data
- **WebApplication** schema — full app description with `featureList`
- Clear, factual, question-answer content that AI can extract and cite
- No keyword stuffing — natural, dense, informative prose

### ✅ GEO (Generative Engine Optimization)
- `<meta name="geo.region" content="BD">` for local signals
- Structured data with `datePublished`, `dateModified`, `inLanguage`
- Author entity (`Person` schema) linked to GitHub
- Concise, authoritative content with real answers (not fluff)

### ✅ Accessibility (a11y)
- ARIA `role`, `aria-label`, `aria-live`, `aria-selected` throughout
- Keyboard navigation (Enter/Space on interactive elements)
- Screen-reader hidden elements via `.sr-only`
- Semantic progressbar with `aria-valuenow`

---

## ❓ FAQ

**Q: Is this tool free?**
A: Yes, completely free and open source (MIT license).

**Q: Does Google officially support this for all websites?**
A: Google officially designed the Indexing API for JobPosting/BroadcastEvent schema. However, many SEOs use it for general URL crawl requests. It triggers faster crawling; indexing is still at Google's discretion.

**Q: My key gives a 403 error — why?**
A: You haven't added the service account email as an **Owner** in Google Search Console. See Step 5 of the setup guide.

**Q: Can I host this myself?**
A: Yes. It's a single HTML file with no dependencies. Upload it anywhere: GitHub Pages, Netlify, Vercel, Cloudflare Pages, or any web host.

**Q: Is my private key safe?**
A: Yes. Your JSON key is only read in-memory in your browser. It's never uploaded to any server. The Web Crypto API signs the JWT locally.

**Q: Why does it show "quota exhausted"?**
A: Each service account key allows 200 URL submissions per day. Add more keys to increase your daily limit.

---

## 🧰 Tech Stack

| Technology | Usage |
|---|---|
| HTML5 | Structure + Semantic markup |
| CSS3 (Custom Properties) | Light theme, glassmorphism, animations, responsive grid |
| Vanilla JavaScript (ES2020) | All app logic, no frameworks |
| Web Crypto API | RSA-SHA256 JWT signing for Google OAuth |
| Google OAuth 2.0 | Access token exchange |
| Google Indexing API v3 | URL submission endpoint |
| localStorage | State persistence (stats + history + key metadata) |
| Schema.org JSON-LD | SEO structured data |

---

## 🤝 Contributing

Contributions are welcome!

1. Fork this repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add: your feature description'`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

### Ideas for Contribution
- [ ] Sitemap XML auto-parser (paste sitemap URL → extract all URLs)
- [ ] CSV import for bulk URLs
- [ ] Export submission log as CSV
- [ ] Dark/Light theme toggle
- [ ] PWA support (offline-capable)
- [ ] Notification sound on completion

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Tanzid Al Tuhin**

- 🌐 Tool: [https://tanzidaltuhin.pro/instant-indexer/](https://tanzidaltuhin.pro/instant-indexer/)
- 💻 GitHub: [@mdtanzidislam](https://github.com/mdtanzidislam)

---

<div align="center">

⭐ **If this tool helped you, please star this repository!** ⭐

Made with ❤️ by Tanzid Al Tuhin · Bangladesh 🇧🇩

</div>
