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
🔒゛Ambil Token mu dan masukan ke dalam environment

Token digunakan untuk masuk ke akun discord bot mu
- 📣゛Discord telah memperbarui keamanan token

Token bot hanya bisa dilihat satu kali, jika kamu lupa, kamu harus regenerasi token yang baru

![Token](./assets/token_dark.png#gh-dark-mode-only)
![Token](./assets/token_light.png#gh-light-mode-only)

## 📦゛Instal Paket
Kamu butuh [`NodeJS`](https://nodejs.org) versi 16 atau 16 keatas

| Paket | Versi |
| - | - |
| 🥥゛[discord.js](https://www.npmjs.com/package/discord.js) `npm i discord.js@13.3.1` | [13.3.1](https://www.npmjs.com/package/discord.js/v/13.3.1) |
| ✨゛[@discordjs/voice](https://www.npmjs.com/package/@discordjs/voice) `npm i @discordjs/voice@0.8.0` | [0.8.0](https://www.npmjs.com/package/@discordjs/voice/v/0.8.0)|
| 🍃゛[ffmpeg-static](https://www.npmjs.com/package/ffmpeg-static) `npm i ffmpeg-static@4.4.1` | [4.4.1](https://www.npmjs.com/package/ffmpeg-static/v/4.4.1) |
| 🌸゛[opusscript](https://www.npmjs.com/package/opusscript) `npm i opussctipt@0.0.8` | [0.0.8](https://www.npmjs.com/package/opusscript/v/0.0.8) |
| 🌙゛[distube](https://www.npmjs.com/package/distube) `npm i distube@3.3.2` | [3.3.2](https://www.npmjs.com/package/distube/v/3.3.2) |
| 🌴゛[@distube/yt-dlp](https://www.npmjs.com/package/@distube/yt-dlp) `npm i @distube/yt-dlp@1.0.2` | [1.0.2](https://npmjs.com/package/@distube/yt-dlp/v/1.0.2) |

## ✨゛Mulai Coding

- Online IDE yang kami gunakan untuk kode ini adalah [`🍫゛Repl.it`](https://replit.com)

### 🍃゛Atur constructor
Impor [`🥥゛Client`](https://github.com/discordjs/discord.js/blob/main/packages/discord.js/src/client/Client.js), [`🌙゛Distube`](https://github.com/skick1234/DisTube/blob/main/src/DisTube.ts), dan [`🌴゛YtDlpPlugins`](https://github.com/distubejs/yt-dlp/blob/main/src/index.ts) dari package
```js
const { Client } = require("discord.js");
const { DisTube } = require("distube");
const { YtDlpPlugins } = require("@distube/yt-dlp");
```
### 🌸゛Buat Client
[`🥥゛Client`](https://github.com/discordjs/discord.js/blob/main/packages/discord.js/src/client/Client.js)
- Client digunakan untuk mengakses bot, intents dibutuhkan untuk construction client, pastikan kamu memasukan inten "GUILDS" untuk mengakses guild, dan "GUILD_VOICE_STATES" untuk mengakses voice state yang ada dalam guild

[`🌙゛Distube`](https://github.com/skick1234/DisTube/blob/main/src/DisTube.ts)
- DisTube digunakan untuk memutar musik, karena opsi `youtubeDL` sudah di TIDAK DIGUNAKAN LAGI, ubah `youtubeDL: false`, dan tambahkan `plugins: [new YtDlpPlugin()]` di opsi distube
```js
const client = new Client({ intents: ["GUILDS", "GUILD_VOICE_STATES"] });
client.player = new DisTube(client, { leaveOnEmpty: false, leaveOnStop: false, youtubeDL: false, plugins: [new YtDlpPlugin()] });
```
### 🌙゛Hubungkan bot
Mulai putar lagu saat client sudah siap
```js
client.on("ready", async client => {
  await console.log(`Masuk sebagai ${client.user.tag}`);
  await client.player.play("ID Channel", "URL Video");
});
```
Impor `token` dari environment
```js
const { token } = process.env;
client.login(token);
```
Kamu juga bisa gunakan cara yang biasa digunakan developer
```js
client.login(token)
```

### ☁️゛Buat webhost untuk replit mu
Salin kode dibawah, dan tempel url mu di [`Uptimerobot`](https://uptimerobot.com)
```js
require("http").createServer((_, res) => res.end("Uptime!")).listen(3000)
```
## 🏓゛Kode Hasil
Ini adalah kode ringkas untuk kalian, jika kalian ingin copy paste😁
```js
//Masukan dalam file index.js
const client = new Client({ intents: ["GUILDS", "GUILD_VOICE_STATES"] });
client.player = new DisTube(client, { leaveOnEmpty: false, leaveOnStop: false, youtubeDL: false, plugins: [new YtDlpPlugin()] });

client.on("ready", async client => {
  await console.log(`Masuk sebagai ${client.user.tag}`);
  await client.player.play("ID Channel", "URL Video");
});

const { token } = process.env;
client.login(token);

require("http").createServer((_, res) => res.end("Uptime!")).listen(3000)
```
