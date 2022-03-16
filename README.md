# Lofi-Bot
Buat bot LoFi mu sendiri✨
![Lofi](./assets/lofi_black.png#gh-dark-mode-only)
![Lofi](./assets/lofi_white.png#gh-light-mode-only)

## 📦゛Instal Paket
- [ ] Software untuk kode ini adalah [`Repl.it`](https://replit.com)
 - Pastikan instal node versi 16 ke atas

| Paket | Versi |
| - | - |
| 🥥゛[discord.js](https://www.npmjs.com/package/discord.js) `npm i discord.js@13.3.1` | [13.3.1](https://www.npmjs.com/package/discord.js/v/13.3.1) |
| ✨゛[@discordjs/voice](https://www.npmjs.com/package/@discordjs/voice) `npm i @discordjs/voice@0.8.0` | [0.8.0](https://www.npmjs.com/package/@discordjs/voice/v/0.8.0)|
| 🍃゛[ffmpeg-static](https://www.npmjs.com/package/ffmpeg-static) `npm i ffmpeg-static@4.4.1` | [4.4.1](https://www.npmjs.com/package/ffmpeg-static/v/4.4.1) |
| 🌸゛[opusscript](https://www.npmjs.com/package/opusscript) `npm i opussctipt@0.0.8` | [0.0.8](https://www.npmjs.com/package/opusscript/v/0.0.8) |
| 🌙゛[distube](https://www.npmjs.com/package/distube) `npm i distube@3.3.2` | [3.3.2](https://www.npmjs.com/package/distube/v/3.3.2) |
| 🌴゛[@distube/yt-dlp](https://www.npmjs.com/package/@distube/yt-dlp) `npm i @distube/yt-dlp@1.0.2` | [1.0.2](https://npmjs.com/package/@distube/yt-dlp/v/1.0.2) |

## ✨゛Mulai Coding

### 🍃゛Atur constructor
```js
const { Client } = require("discord.js");
const { DisTube } = require("distube");
const { YtDlpPlugins } = require("@distube/yt-dpl");
```
### 🌸゛Buat Client
```js
const client = new Client({ intents: ["GUILDS", "GUILD_VOICE_STATES"] });
client.player = new DisTube(client, { leaveOnEmpty: false, leaveOnStop: false, youtubeDL: false, plugins: [new YtDlpPlugin()] });
```
### 🌙゛Hubungkan bot
```js
client.on("ready", async client => {
  await console.log(`Masuk sebagai ${client.user.tag}`);
  await client.player.play("ID Channel", "URL Video");
});
```
Masukan token bot di environment mu!
```js
const { token } = process.env;
```
```js
client.login(token);
```

### ☁️゛Buat webhost untuk replit mu
```js
require("http").createServer((_, res) => res.end("Uptime!")).listen(3000)
```
