# Disvas
Image manipulation tool to manipulate images!

# Installation
```sh
$ npm i disvas
```

[![NPM](https://nodei.co/npm/disvas.png)](https://nodei.co/npm/disvas/)

# Documentation
Coming soon!

# Examples
> ## Atomize
```js
const { Client, MessageAttachment, Intents } = require("discord.js");
const client = new Client({ intents: ["GUILDS", "GUILD_MESSAGES"] })
const disvas = require("disvas");

client.on("ready", () => {
    console.log("Bot is online!");
});

client.on("messageCreate", async (message) => {
    if (message.author.bot) return;
    if (message.content === "!atomize") {
        let avatar = message.author.displayAvatarURL({ format: 'png' });
        let buffer = await disvas.Canvas.atomize(avatar);
        let attachment = new MessageAttachment(buffer, "Amotize.gif");
        return message.channel.send({ files:[attachment] });
    }
});
client.login(token)
```

> ## Text on Avatar
```js
const { Client, MessageAttachment, Intents } = require("discord.js");
const client = new Client({ intents: ["GUILDS", "GUILD_MESSAGES"] })
const disvas = require("disvas");

client.on("ready", () => {
    console.log("Bot is online!");
});

client.on("messageCreate", async (message) => {
    if (message.author.bot) return;
    if (message.content === "!textOnAvatar") {
        let avatar = message.author.displayAvatarURL({ format: 'png' });
        let args = message.content.split(" ").slice(1);
        let buffer = await disvas.Canvas.textOnAvatar(avatar, args);
        let attachment = new MessageAttachment(buffer, "TextOnAvatar.gif");
        return message.channel.send({ files:[attachment] });
    }
});
client.login(token)
```

> ## Rain
```js
const { Client, MessageAttachment, Intents } = require("discord.js");
const client = new Client({ intents: ["GUILDS", "GUILD_MESSAGES"] })
const disvas = require("disvas");

client.on("ready", () => {
    console.log("Bot is online!");
});

client.on("messageCreate", async (message) => {
    if (message.author.bot) return;
    if (message.content === "!rain") {
        let avatar = message.author.displayAvatarURL({ format: 'png' });
        let buffer = await disvas.Canvas.rain(avatar);
        let attachment = new MessageAttachment(buffer, "Rain.gif");
        return message.channel.send({ files:[attachment] });
    }
});
client.login(token)
```

> ## Freeze
```js
const { Client, MessageAttachment, Intents } = require("discord.js");
const client = new Client({ intents: ["GUILDS", "GUILD_MESSAGES"] })
const disvas = require("disvas");

client.on("ready", () => {
    console.log("Bot is online!");
});

client.on("messageCreate", async (message) => {
    if (message.author.bot) return;
    if (message.content === "!freeze") {
        let avatar = message.author.displayAvatarURL({ format: 'png' });
        let buffer = await disvas.Canvas.freeze(avatar);
        let attachment = new MessageAttachment(buffer, "Freeze.gif");
        return message.channel.send({ files:[attachment] });
    }
});
client.login(token)
```

> ## FakeMessage [BETA]
```js
const { Client, MessageAttachment, Intents } = require("discord.js");
const client = new Client({ intents: ["GUILDS", "GUILD_MESSAGES"] })
const disvas = require("disvas");

client.on("ready", () => {
    console.log("Bot is online!");
});

client.on("messageCreate", async (message) => {
    if (message.author.bot) return;
    if (message.content === "!fakeMessage") {
        let name = message.author.username;
        let avatar = message.author.displayAvatarURL({ format: 'png' });
        let hex = "#ffffff";
        let content = message.content;
        let buffer = await disvas.Canvas.fakeMessage(name, avatar, hex, content);
        let attachment = new MessageAttachment(buffer, "FakeMessage.png");
        return message.channel.send({ files:[attachment] });
    }
});
client.login(token)
```

## Contributors

#### Big thanks to these people, without them, this project wouldn't be possible!
<a href = "https://github.com/hisRoyalty/Disvas/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=hisRoyalty/Disvas"/>
</a>


# Note
> Work in progress!
