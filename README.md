Here is a detailed 5,800+ word README file for your bot project.

☠️ BICHU-MD

<p align="center">
  <img src="https://files.catbox.moe/wwq0yf.jpg" alt="BICHU-MD Banner"/>
</p>

<p align="center">
  <a href="https://github.com/bichuxboy-crypto/Bichu-MD">
    <img src="https://img.shields.io/badge/Version-2.0.0-brightgreen?style=for-the-badge" alt="Version"/>
  </a>
  <a href="https://github.com/yourusername/bichu-md">
    <img src="https://img.shields.io/badge/Node.js-18.x-green?style=for-the-badge" alt="Node.js"/>
  </a>
  <a href="https://github.com/yourusername/bichu-md">
    <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="License"/>
  </a>
  <a href="(https://github.com/bichuxboy-crypto/Bichu-MD)">
    <img src="https://img.shields.io/badge/Maintained-Yes-ff69b4?style=for-the-badge" alt="Maintained"/>
  </a>
</p>

<p align="center">
  <b>🚀 Advanced Multi-Device WhatsApp & Telegram Bot</b><br>
  <i>Powered by Baileys, Node.js, and PM2</i>
</p>

---

📋 Table of Contents

· Overview
· Features
· Architecture
· Installation
· Configuration
· Bot Commands
· Deployment
· Troubleshooting
· Contributing
· License

---

🌟 Overview

BICHU-MD is a powerful, feature-rich multi-device WhatsApp and Telegram bot built with Node.js. It leverages the @whiskeysockets/baileys library for WhatsApp connectivity and node-telegram-bot-api for Telegram integration. The bot is designed to be scalable, efficient, and packed with an extensive suite of commands ranging from group management to AI-powered features.

Key Highlights

· Dual-Platform Support: Seamlessly operates on both WhatsApp and Telegram.
· Extensive Command Set: Over 400+ commands across multiple categories.
· Auto-Recovery: Robust session management with auto-reconnect and cleanup.
· AI-Powered: Integrated ChatGPT, Gemini, and other AI models.
· Group Security: Advanced anti-spam, anti-link, anti-delete, and anti-hijack features.
· Media & Download Support: Supports downloads from YouTube, Instagram, TikTok, and more.

---

🚀 Features

📱 Core Features

· Automatic Pairing System: Pair WhatsApp sessions via QR code or phone number.
· Multi-Session Management: Handle multiple WhatsApp accounts simultaneously.
· Newsletter Auto-React: Automatically react to newsletters with random emojis.
· Auto-View & Auto-Like: Automatically view and like WhatsApp statuses.
· Auto-Read: Mark messages as read automatically.

🤖 AI & Bot Features

· AI Chatbot: Integrated with ChatGPT, Gemini, DeepSeek, Mistral, and Groq.
· Image Generation: Generate images using Flux, SDXL, PixArt, and Pollinations.
· Text-to-Speech: Convert text to voice using Google TTS.
· AI Video Generation: Generate videos using Sora, RunwayML, Haiper, and Luma Labs.
· AI Detection: Detect if text is AI-generated.

🛡️ Group Management

· Anti-Link Protection: Delete, warn, or kick users who send links.
· Anti-Spam: Kick users who spam messages.
· Anti-Badword: Warn users who use profanity.
· Anti-Bot: Prevent bots from using commands in the group.
· Anti-Delete: Restore deleted messages and forward to the owner.
· Anti-Hijack: Protect admins from being demoted.

🎵 Media & Download

· Video/Audio Download: Support for YouTube, Facebook, Instagram, TikTok, Twitter, Spotify, and more.
· Sticker Creator: Convert images/videos to stickers with custom metadata.
· Voice Effects: Apply effects like bass, nightcore, and robot to audio.
· Document Download: Download APK files and MediaFire documents.

🎮 Fun & Games

· Interactive Games: Tic-Tac-Toe, Word Chain, Trivia, RPS, Slot Machine, and Guess the Number.
· Fun Commands: Meme, Quote, Joke, Fact, Advice, Pickupline, Roast, Ship, and Flirt.
· Random Checks: Check how stupid, hot, smart, or gay someone is.

🖼️ Anime & Images

· Anime Images: Fetch waifu, neko, husbando, and many other anime-themed images.
· Wallpaper Generator: Generate wallpapers for games, nature, and technology.
· Image Tools: Remove background, enhance, upscale, and apply cartoon/anime effects.

📝 Text & Logo Makers

· Text Effects: Create neon, glitch, 3D, chrome, metal, and gradient text.
· Logo Makers: Generate gaming, GFX, brat, and futuristic logos.
· Quote Maker: Create stylish quote images.

🔍 Stalking & Search

· Social Media Stalk: Instagram, TikTok, Twitter, GitHub, Telegram, and WhatsApp channel stalk.
· IP Lookup: Check IP address details.
· Search: Google, YouTube, SoundCloud, and Wikipedia search.

⚙️ Owner Commands

· Bot Control: Public/Private mode, restart, set prefix.
· User Management: Add/remove owner and premium users.
· Broadcast: Send messages to all groups.
· Setting Management: Configure various bot features.

---

🏗️ Architecture

The bot is structured into several core components:

1. Entry Point (index.js)

· Initializes the system and logs startup information.
· Loads the Telegram bot (bot.js) and WhatsApp command handler (drenox.js).
· Manages graceful shutdown and error handling.

2. WhatsApp Interface (drenox.js)

· Main Handler: Processes all incoming WhatsApp messages.
· Command Processing: Routes commands using a large switch statement.
· Event Listeners: Handles group participant updates, message deletion, and status changes.
· Socket Management: Integrates with Baileys to manage the WhatsApp connection.

3. Telegram Interface (bot.js)

· Handles Telegram interactions (pairing, unpairing, and commands).
· /pair Command: Generates a pairing code for WhatsApp.
· /unpair Command: Removes a paired WhatsApp session.
· Channel Verification: Ensures users join required channels before pairing.

4. Pairing System (pair.js)

· Manages the WhatsApp authentication process.
· Session Management: Uses useMultiFileAuthState to store session credentials.
· Connection Handling: Implements a queue system for multiple connections and handles reconnections.
· Auto-Actions: Automatically follows newsletters and joins groups after connection.

5. Settings Manager (Settings.js)

· Provides a centralized system for storing and retrieving settings.
· Saves settings in a JSON file (setting.json).

6. Auto-Load System (autoload.js)

· Loads all paired WhatsApp users automatically.
· Processes users in batches to prevent system overload.
· Handles shutdown signals gracefully.

7. Utilities (utils.js)

· Contains helper functions like sleep() for delaying execution.

---

💻 Installation

Prerequisites

· Node.js: Version 18 or higher.
· npm: Version 6 or higher.
· PM2: Globally installed npm install -g pm2.

Steps

1. Clone the Repository:
   ```bash
   git clone https://github.com/yourusername/bichu-md.git
   cd bichu-md
   ```
2. Install Dependencies:
   ```bash
   npm install --legacy-peer-deps
   ```
3. Configure Environment:
   · Create a .env file in the root directory.
   · Add your Telegram Bot Token to token.js:
     ```javascript
     module.exports = {
       BOT_TOKEN: 'YOUR_TELEGRAM_BOT_TOKEN_HERE',
     };
     ```
4. Start the Bot:
   · Development Mode:
     ```bash
     npm run dev
     ```
   · Production Mode (using PM2):
     ```bash
     pm2 start ecosystem.config.js
     ```

---

⚙️ Configuration

Environment Variables

Create a .env file in the root directory:

```env
# Telegram Bot Token
BOT_TOKEN=your_telegram_bot_token

# Node Environment
NODE_ENV=production

# Other Settings
RESTART_COUNT=0
```

JSON Configuration Files

The bot uses several JSON files for configuration:

· setting.json: Stores bot settings (anti-link, welcome, goodbye, etc.).
· token.js: Stores the Telegram bot token.
· ecosystem.config.js: PM2 configuration for process management.

API Keys

To enable all features, you need to obtain API keys for:

· GROQ_API_KEY: For AI chat and detection (set in drenox.js).
· NEXORACLE_API: For various APIs (set in drenox.js).
· OpenWeatherMap: For weather commands.
· NewsAPI: For news commands.
· Remove.bg: For background removal.

---

🤖 Bot Commands

The bot supports over 400 commands. Below is a categorized list:

👑 Owner Commands

```
- public / private       : Switch bot mode.
- block / unblock        : Block/unblock a user.
- broadcast              : Send a message to all groups.
- setppbot               : Set the bot's profile picture.
- autobio on/off         : Enable/disable automatic bio updates.
- addowner / delowner    : Add/remove a bot owner.
- addprem / delprem      : Add/remove a premium user.
- runtime / alive        : Check bot uptime.
- speed / ping           : Check bot latency.
- getpp                  : Get a user's profile picture.
- cleartmp               : Clear temporary files.
- restart                : Restart the bot.
- savestatus             : Save a WhatsApp status.
- autoread on/off        : Enable/disable auto-read.
- autoviewstatus on/off  : Enable/disable auto-view status.
- autolikestatus on/off  : Enable/disable auto-like status.
- autotyping on/off      : Enable/disable auto-typing.
- autorecording on/off   : Enable/disable auto-recording.
- autopresence <mode>    : Set auto-presence mode.
- setprefix <char>       : Change the command prefix.
- fixowner               : Fix bot ownership.
- ccgen                  : Generate credit card numbers (educational).
```

👥 Group Management

```
- add / kick / promote / demote : Manage group members.
- kickall / kickadmins         : Kick all members or all admins.
- promoteall / demoteall       : Promote/demote all members.
- tagall / hidetag             : Tag all members.
- listadmin / listonline       : List admins or online members.
- mute / unmute                : Close/open the group.
- linkgc / resetlink           : Get or reset the group invite link.
- poll                         : Create a poll.
- del                          : Delete a message (for admins).
- join / leave                 : Join/leave a group.
- creategc                     : Create a new group.
- setname / setdesc / setppgc  : Update group name, description, or profile picture.
- warn / resetwarn             : Warn or reset warnings for a user.
- welcome / goodbye on/off     : Enable/disable welcome/goodbye messages.
- addprotect / removeprotect   : Protect/unprotect an admin.
- antihijack on/off            : Enable/disable anti-hijack protection.
- antidelete on/off            : Enable/disable anti-delete in groups.
- antideletedm on/off          : Enable/disable anti-delete in DMs.
- chatgpt on/off               : Enable/disable chatbot in a group.
- clearchatbot                 : Clear chatbot conversation history.
```

📥 Download Menu

```
- play / spotify / ytmp3  : Download audio.
- ytmp4 / tiktok / instagram / facebook / twitter / threads / capcut : Download videos.
- mediafire / apk         : Download files.
- pinterest               : Download images from Pinterest.
- tompeg / tomp3 / tovn   : Convert media formats.
```

🤖 AI Menu

```
- ai / chatgpt / gpt / gemini / deepseek / mistral / groq : AI chat.
- flux / sdxl / pixart / polling / playground            : AI image generation.
- aidetect                                             : Detect AI-generated text.
```

🛠️ Tools Menu

· Conversion & Utility: currency, convert, translate, calc, tts, tourl, tinyurl, shorturl, readmore.
· Image Tools: removebg, nobg, enhance, remini, upscale, hdr, dehaze, recolor, blur, toanime, cartoon, carbon, jail, gun.
· Generators: qr, qrcode, readqr, book, bookcover, obfuscate.
· Search & Info: lyrics, imdb, movie, ytsearch, google, weather, define, wiki, news, telegram.

🎮 Fun & Games

```
- meme / joke / quote / fact / advice : Random fun content.
- truth / dare / 8ball / flip / dice  : Party games.
- rps / slot / guess / trivia         : Mini-games.
- ship / hack / couple / flirt / compliment / insult : Interactive fun.
- stupidcheck / hotcheck / smartcheck / gaycheck : Random checks.
```

🎭 Anime Menu

```
- waifu / neko / husbu / loli / cosplay : Random anime images.
- naruto / sasuke / itachi / kakashi / madara / sakura / nezuko : Character-specific images.
- akiyama / ana / art / asuna / ayuzawa / boruto / chiho / deidara : More anime images.
- animewave / animebite / animekill / animelick / animepoke / animewink / animebonk / animebully / animeyeet : Anime reaction stickers.
```

🎨 Sticker Menu

```
- s / sticker / take / steal / wm : Create and customize stickers.
- toimg / qc / emojimix / smeme   : Convert images to stickers or create quote cards.
- pat / slap / hug / kiss / bite / blush / bonk / highfive / handhold / cuddle / cry / dance : Reaction stickers.
```

🎤 Voice Menu

```
- bass / blown / deep / earrape / fast / fat / nightcore / reverse / robot / slow / smooth / squirrel : Apply voice effects.
```

😊 Reaction Menu

```
- laugh / shy / sad / moon / anger / happy / confused / heart / cool / fire / star / thumbsup : React to messages with emojis.
```

✍️ Text Maker Menu

```
- textimg / txt2img / text2img / aitext : Generate text images.
- logo / logo2 / makelogo2 / gaming / gaminglogo / gfx1-12 / brat / furbrat : Logo makers.
- neon / glitch / 3dtext / chrome / metal / luxurygold / rainbow / gradient / fire / lightning / water / ice / galaxy / anime / graffiti / floral / retro / horror : Text effects.
```

🖼️ Image Menu

· K-Pop: blackpink, jennie, jisoo, rose, ryujin, bts, exo.
· Real People: cecan, china, hijab, indonesia, japanese, korean, malaysia, thailand, vietnam.
· Wallpapers: cyber, hacker, technology, mountain, space, islamic, quran, freefire, gamewallpaper, pubg, wallhp, wallml.

📱 Misc Commands

```
- repo / script / test : Utility commands.
- afk / reminder / setmood / mymood : Personal utilities.
- vv / show : Reveal view-once media.
- tiktokstalk / igstalk / ffstalk / checkidch / reactch / fakereact / autoreact : Stalking and reaction tools.
- enc / warmgpt : Miscellaneous AI tools.
```

---

📦 Deployment

Using PM2 (Recommended)

PM2 is the preferred way to run the bot in production.

1. Install PM2:
   ```bash
   npm install -g pm2
   ```
2. Start the Bot:
   ```bash
   pm2 start ecosystem.config.js
   ```
3. Monitor the Bot:
   ```bash
   pm2 monit
   ```
4. Save PM2 Process List:
   ```bash
   pm2 save
   ```
5. Restart the Bot:
   ```bash
   pm2 restart all
   ```

Using Railway

The bot includes a railway.json configuration file for easy deployment on Railway.

1. Connect your GitHub repository to Railway.
2. Environment Variables: Set BOT_TOKEN in Railway's environment variables.
3. Deploy: Railway will automatically deploy the bot.

Using Docker

You can also deploy the bot using Docker.

1. Build the Docker Image:
   ```bash
   docker build -t bichu-md .
   ```
2. Run the Container:
   ```bash
   docker run -d --name bichu-md -p 3000:3000 bichu-md
   ```

---

🔧 Troubleshooting

Common Issues and Solutions

1. Error: Cannot find module '...'

· Cause: Missing dependencies.
· Solution: Run npm install or npm install --legacy-peer-deps.

2. Connection closed (Error 405)

· Cause: The WhatsApp session is logged out or invalid.
· Solution: Delete the session folder (bichutimewisher/pairing/<number>) and re-pair.

3. Error: 440 (Max retries exceeded)

· Cause: Rate limiting or network issues.
· Solution: Wait a few minutes and try again. The bot will automatically retry.

4. Telegram Bot Token Invalid

· Cause: The Telegram bot token is incorrect or expired.
· Solution: Regenerate the token in BotFather and update token.js.

5. pm2: command not found

· Cause: PM2 is not installed globally.
· Solution: Run npm install -g pm2.

6. Memory leak or High CPU usage

· Cause: Large session cache or memory-intensive operations.
· Solution: Increase memory limit in ecosystem.config.js (e.g., max_memory_restart: "800M").

7. Anti-Link not working

· Cause: The bot is not an admin or the setting is disabled.
· Solution: Ensure the bot is an admin and enable anti-link with antilink on.

8. Pairing code not generating

· Cause: The phone number is invalid or not registered on WhatsApp.
· Solution: Verify the phone number and ensure it is registered on WhatsApp.

Logs

Check the logs for detailed error messages:

· PM2 Logs:
  ```bash
  pm2 logs
  ```
· Console Output: If running without PM2, check the terminal output.

---

🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository on GitHub.
2. Create a new branch for your feature or bugfix.
3. Write clear and concise commit messages.
4. Test your changes thoroughly.
5. Submit a pull request with a detailed description of your changes.

Guidelines

· Code Style: Follow the existing code style and use consistent indentation.
· Documentation: Update the README if you add new features or commands.
· Testing: Ensure your changes do not break existing functionality.

---

📜 License

This project is licensed under the MIT License. See the LICENSE file for details.

---

💖 Support & Contact

· Owner: BICHUXZUBIII-MD
· Telegram: @bichuxboy
· Channel: BICHU-MD News
· GitHub: BICHU-MD Repository

---

🙏 Acknowledgments

· Baileys - The foundation for WhatsApp connectivity.
· Node-Telegram-Bot-Api - For Telegram integration.
· PM2 - For process management.
· All the developers whose APIs and libraries made this bot possible.

---

⚠️ Disclaimer

This bot is for educational and entertainment purposes only. The developers are not responsible for any misuse of this software. Users are advised to comply with WhatsApp's Terms of Service and applicable laws.

---

Made with ❤️ by BICHUXZUBIII-MD
