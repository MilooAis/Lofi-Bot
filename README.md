# ☁️゛Lofi-Bot
Buat bot LoFi mu sendiri✨
![Lofi](./assets/lofi_black.png#gh-dark-mode-only)
![Lofi](./assets/lofi_white.png#gh-light-mode-only)

## 🍉゛Setup Bot
### 🥥゛Buat Aplikasi

🌿゛Buat aplikasi di [`Portal pengembang Discord`](https://discord.com/developers/applications)

![Application](./assets/aplikasi_dark.png#gh-dark-mode-only)
![Application](./assets/aplikasi_light.png#gh-light-mode-only)

🗞️゛Atur icon dan deskripsi

Deskripsi aplikasi akan diletakkan di deskripsi akun (About Me) bot Discord mu

![Setting](./assets/setting_dark.png#gh-dark-mode-only)
![Setting](./assets/setting_light.png#gh-light-mode-only)

### ☁️゛Ubah Akun Bot
🔒゛Ambil Token mu

Token digunakan untuk masuk ke akun discord bot mu
- 📣゛Discord telah memperbarui keamanan token
Token bot hanya bisa dilihat satu kali, jika kamu lupa, kamu harus regenerasi token yang baru

![Token](./assets/token_dark.png#gh-dark-mode-only)
![Token](./assets/token_light.png#gh-light-mode-only)

## 📦゛Instal Paket
- [ ] Online IDE yang kami gunakan untuk kode ini adalah [`🍫゛Repl.it`](https://replit.com)
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
Impor [`🥥゛Client`](https://github.com/discordjs/discord.js/blob/main/packages/discord.js/src/client/Client.js), [`🌙゛Distube`](https://github.com/skick1234/DisTube/blob/main/src/DisTube.ts), dan [`🌴゛YtDlpPlugins`](https://github.com/distubejs/yt-dlp/blob/main/src/index.ts) dari package
```js
const { Client } = require("discord.js");
const { DisTube } = require("distube");
const { YtDlpPlugins } = require("@distube/yt-dlp");
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
