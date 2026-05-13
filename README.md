# 🔗 Advanced Link Extractor

A powerful, client-side link extraction tool that runs entirely in the browser — no server, no installs, no data sent anywhere.

![HTML](https://img.shields.io/badge/HTML-5-orange?logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-3-blue?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES2020-yellow?logo=javascript&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)
![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-compatible-brightgreen?logo=github)

---

## ✨ Features

- **Three input modes** — extract links from a live URL, pasted text, or an uploaded file
- **Smart URL detection** — finds links with protocols (`https://`), bare `www.` domains, and plain domain names with common TLDs
- **CORS proxy support** — use AllOrigins or CORS Proxy IO to reach sites that block direct browser requests
- **Filtering** — exclude links by domain or keyword, applied instantly
- **Deduplication** — automatically removes duplicate URLs
- **URL normalization** — prepends `https://` to protocol-less links
- **Punctuation cleaning** — strips trailing commas, brackets, and other punctuation that can bleed into URLs
- **Link verification** — optionally pings each link (HEAD request) and removes unreachable ones
- **Sorting** — alphabetical (A–Z / Z–A), by length (shortest / longest), or by domain
- **File format support** — `.txt`, `.html`, `.htm`, `.md`, `.xml`, `.json`
- **Export** — copy all links to clipboard or save as a `.txt` file
- **Dark mode** — follows your system preference automatically
- **Fully accessible** — keyboard navigation, ARIA roles, focus management

---

## 🚀 Live Demo

Hosted on GitHub Pages: **[https://nuhbodyok.github.io/linkex/]**

---

## 📦 Getting Started

No build step required. It's a single HTML file.

### Use locally

```bash
git clone https://github.com/your-username/link-extractor.git
cd link-extractor
open Link_Extractor.html   # or just double-click it
```

### Deploy to GitHub Pages

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set the source to the `main` branch, root directory
4. Your tool will be live at `https://your-username.github.io/link-extractor/Link_Extractor.html`

---

## 🖥️ Usage

### URL mode
Paste any URL and click **Extract Links**. The tool attempts a direct fetch first; if that's blocked by CORS, it falls back to a proxy. You can choose the proxy strategy in **Advanced Options**.

### Text mode
Paste any block of text — emails, markdown, source code, log files — and all URLs will be extracted automatically.

### File mode
Upload a local file. Supported formats:

| Format | How links are found |
|--------|-------------------|
| `.html` / `.htm` | `<a href>`, `[src]` attributes, meta tags, inline text |
| `.json` | Recursively searches all string values |
| `.xml` | All element text content and attribute values |
| `.txt` / `.md` | Plain text URL matching |

### Filters & options

| Option | Description |
|--------|-------------|
| Domain filter | Exclude all links matching a hostname (e.g. `ads.example.com`) |
| Keyword filter | Exclude links containing a word (e.g. `login`, `cdn`) |
| Remove duplicates | Keep only the first occurrence of each URL |
| Normalize URLs | Add `https://` to links that are missing a protocol |
| Clean punctuation | Strip trailing `. , ; ) ]` characters from URLs |
| Verify links | Send a HEAD request to each link and remove unreachable ones |

---

## 🧩 CORS & Fetching

Browsers block cross-origin requests by default. The tool handles this in layers:

1. **Direct fetch** — attempted first (works for permissive or same-origin sites)
2. **AllOrigins** (`api.allorigins.win`) — free proxy, good general coverage
3. **CORS Proxy IO** (`corsproxy.io`) — alternative proxy
4. **Fallback** — if everything fails, the entered URL itself is returned as a single result

You can configure the proxy strategy under **Advanced Options** in URL mode.

> **Note:** CORS proxies are third-party services. Don't use them for sensitive or private URLs.

---

## 🗂️ Project Structure

```
link-extractor/
└── Link_Extractor.html   # entire app — HTML, CSS, and JS in one file
```

---

## 🌐 Browser Compatibility

Works in all modern browsers. No polyfills or transpilation needed.

| Browser | Support |
|---------|---------|
| Chrome / Edge | ✅ Full |
| Firefox | ✅ Full |
| Safari | ✅ Full |
| Mobile (iOS / Android) | ✅ Full |

---

## 🤝 Contributing

Contributions are welcome! To get started:

```bash
git clone https://github.com/your-username/link-extractor.git
```

Open `Link_Extractor.html` in a browser and start editing — changes are reflected on reload. No build tooling required.

Please open an issue before submitting large changes so we can discuss the approach first.

---

## 📄 License

[MIT](LICENSE) — free to use, modify, and distribute.
