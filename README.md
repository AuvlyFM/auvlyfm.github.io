# 🎵 TuneCharts

A suite of visual tools for music lovers, integrated with Last.fm and Spotify APIs. This project generates aesthetic reports ("receipts"), listening statistics, and music compatibility analysis, optimized for social sharing (Instagram Stories).

This repository is a **Monorepo** hosting three distinct tools in subdirectories, serving both the main domain and its subdomains.

## 📂 Project Structure

The project is organized to handle multiple tools within a single repository:

```text
tunecharts/
├── index.html          
├── assets/             
├── css/ & js/          
│
├── counter/            
│   ├── index.html
│   ├── assets/         
│   └── ...
│
├── matcher/            
│   ├── index.html
│   ├── assets/         
│   └── ...
│
├── live/            
│   ├── index.html
│   ├── live.html (The brain)
│   └── ...
```

## 🛠️ Tools & Features
### 1. TuneCharts (Main)

Generates visual cards summarizing top albums, artists, and tracks over customizable periods.

- Focus: Aesthetics and shareability (9:16 format).

- Tech: Canvas generation for instant download.

### 2. Counter (/counter)

Calculates the total time (hours/minutes) a user has spent listening to music.

- Methodology: To ensure mobile performance and avoid API rate limiting, this tool analyzes the user's Top 1,000 Tracks.

- Disclaimer: While this covers 99% of listening time for most users, tracks ranked below 1,000 are not included in the total sum. This decision prioritizes speed and stability over "forensic" precision found in slower, aggressive scrapers.

- UI: Includes an informational modal explaining this calculation logic to the user.

### 3. Matcher (/matcher)

A compatibility tool that cross-references listening history between two users to generate a "Match Score" based on shared artists and genres.

### 4. Live (/live)

A real-time "Always-On Display" visualizer that transforms your monitor into a dynamic music frame.

- Functionality: Continuously monitors your Last.fm "Now Playing" status. When a song starts, it fetches high-resolution album art or artist imagery from Spotify to create a beautiful, immersive backdrop.

- Platform Limitation: Desktop & Tablet Only.

- Reasoning: This tool is designed to function as a digital photo frame or a "Zen Mode" companion for your second monitor while you work or relax. To preserve this specific immersive aesthetic, the interface is restricted on mobile devices (smartphones).

- Features: Real-time polling (updates automatically without refresh).

- Customization Menu: Toggle artist/track names, choose background modes (Artist Image, Album Art, or Solid Color), and adjust layout positions.

- Idle Mode: Automatically detects when music stops.

## ⚠️ Security & API Usage

This project relies on client-side calls to public APIs (Last.fm & Spotify).

API Keys: API Keys used in frontend JavaScript are publicly visible by design.

**Important for Forks:**

- Please generate your own API Keys via the Last.fm API Console and Spotify for Developers.

- NEVER commit a Spotify **"Client Secret"** to a public repository. If backend authentication is needed, use environment variables or a server-side proxy.

- Be mindful of API rate limits.

## 🚀 Deployment & Workflow

This project utilizes a direct-to-production workflow tailored for Hostinger:

- Development: Edits are made directly in the Hostinger environment (or local setup).

- Version Control: Changes are pushed from the server terminal to GitHub for backup/versioning.

## Typical Workflow
git add .
git commit -m "Update feature X"
git push origin main

📄 License & Credits

Developed by [Snow Mint](https://github.com/snw-mint/). TuneCharts is not affiliated with Last.fm or Spotify. Data is provided courtesy of their respective public APIs.
