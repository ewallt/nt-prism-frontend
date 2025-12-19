# NT Exegetical Prism - Frontend

Interactive web application for multi-lens biblical text analysis powered by Claude AI.

## Overview

The NT Exegetical Prism provides in-depth analysis of New Testament passages through multiple interpretive lenses, combining English and Greek texts with commentary, historical context, theological perspectives, and word studies.

## Features

### Dual Study Modes

**⚡ Quick Study Mode**
- Analyze up to 7 verses
- 3 essential lenses: Text, Commentary, Context
- Fast loading (~15-20 seconds)
- Cost: ~3¢ per analysis

**🔬 Deep Study Mode**
- Analyze up to 3 verses
- All 6 analytical lenses
- Comprehensive theological analysis
- Cost: ~5¢ per analysis

### Six Analytical Lenses

1. **📖 Text & Parsing** - ESV English + Greek NA28 text
2. **✍️ Commentary** - Matthew Henry-style insights
3. **🧩 Logical Flow** - Argument structure and rhetorical strategy
4. **📜 Historical Context** - Cultural and historical background
5. **⛪ Theological Traditions** - Reformed, Catholic, Orthodox perspectives
6. **🔍 Word Studies** - Greek morphology and semantic analysis

## Technology

- **Frontend**: Vanilla JavaScript, Tailwind CSS
- **AI Backend**: Claude Sonnet 4 (via Anthropic API)
- **Backend Proxy**: Express.js on Render
- **Deployment**: GitHub Pages (static hosting)

## Architecture

```
Browser → GitHub Pages (Frontend)
           ↓
    Render (Backend Proxy)
           ↓
    Anthropic Claude API
```

The backend proxy is required because Claude API doesn't allow direct browser requests (CORS). The proxy securely stores the API key and forwards requests.

## Setup

### Prerequisites
- Backend deployed to Render (see [nt-prism-backend](https://github.com/ewallt/nt-prism-backend))
- Backend URL configured in `index.html` (line 394)

### Local Development

1. Clone this repository
2. Serve locally:
```bash
python3 -m http.server 8000
```
3. Open `http://localhost:8000`

### GitHub Pages Deployment

1. Push to GitHub
2. Go to **Settings** → **Pages**
3. Source: **Deploy from branch**
4. Branch: **main** → **/ (root)**
5. Save

Your site will be live at: `https://ewallt.github.io/nt-prism-frontend/`

## Usage

1. Select study mode (Quick or Deep)
2. Choose a New Testament book
3. Enter verse reference (e.g., `3:16` or `5:12-18`)
4. Click "Analyze 🚀"
5. Navigate between analytical lenses using tabs

## Cost Considerations

**Claude API Costs:**
- Input: ~$3 per million tokens
- Output: ~$15 per million tokens
- Typical Quick Study (7 verses): ~3¢
- Typical Deep Study (3 verses): ~5¢

**Render Backend:**
- Free tier: 750 hours/month
- Service sleeps after 15 min inactivity
- Cold start: ~30 seconds

## Browser Compatibility

- Modern browsers with ES6+ support
- Chrome, Firefox, Safari, Edge (latest versions)
- Mobile responsive

## Related Repositories

- **Backend**: [nt-prism-backend](https://github.com/ewallt/nt-prism-backend)

## License

MIT

## Credits

- **UI Design**: Custom dark/gold aesthetic inspired by traditional biblical scholarship
- **Typography**: EB Garamond (biblical text), Inter (UI), Crimson Text (accents)
- **AI Provider**: [Anthropic Claude](https://www.anthropic.com/)
- **Biblical Text**: ESV English, NA28 Greek
