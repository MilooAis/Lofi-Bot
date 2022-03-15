# Lofi-Bot
Buat bot LoFi mu sendiri✨
![Lofi](./assets/lofi_black.png#gh-dark-mode-only)
![Lofi](./assets/lofi_white.png#gh-light-mode-only)

## Instal Paket
* [ ] discord.js
* [ ] @discordjs/voice
* [ ] ffmpeg-static
* [ ] opusscript
* [ ] distube
* [ ] @distube/yt-dpl

## Mulai Coding

### Mengatur constructor
```js
const { Client } = require("discord.js");
const { DisTube } = require("distube");
const { YtDplPlugins } = require("@distube/yt-dpl");
```
### Membuat Client
```js
const client = new Client({ intents: ["GUILDS", "GUILD_VOICE_STATES"] });
client.player = new DisTube( client, { leaveOnEmpty: false, leaveOnStop: false, youtubeDL: false, plugins: [new YtDlpPlugin()] });
```
