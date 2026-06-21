# IP Scanner — Telegram Mini App

`scanner.html` is a fully client-side Cloudflare clean-IP scanner + config optimizer.
No server needed — it runs in the user's browser (inside Telegram's WebApp container).

## Host it (static, free)
1. Upload `scanner.html` to **GitHub Pages** or **Cloudflare Pages** (any static HTTPS host).
2. Copy its HTTPS URL, e.g. `https://yourname.github.io/scanner.html`.
3. Put it in the bot's `.env`:  `WEBAPP_URL=https://yourname.github.io/scanner.html`
4. Restart the bot. A **🛰 اسکنر IP کلودفلر** button appears in the main menu and opens
   the app inside Telegram (no extra BotFather setup needed for inline web_app buttons).

## What it does
- Pulls Cloudflare IP ranges (with a built-in fallback list), samples random IPs, and
  latency-tests them from the user's own connection across the chosen port.
- Shows ranked clean IPs; tap to copy.
- Optimizer step: paste vless/vmess/trojan/ss configs and rebuild them with the best
  clean IPs (copy with or without the ping tag).

Note: browser latency is approximate (TLS/handshake timing via fetch), and results
depend on the user's network — same limitation as any in-browser CF scanner.
