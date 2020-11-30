# Yuri-Canvas
yuricanvas is a wrapper for canvas & jimp which can be used to create/manipulate images easily. 
This package is meant for beginners who don't know how to use canvas & stuffs.

> ⚠ This package is not recommended to you if you know how to use canvas/other image manipulation tools.

# Installing

```bash
npm i --save yuri-canvas
```

# Features
- Beginner friendly
- Supports Buffer or image url
- Super fast image manipulation
- Welcomer and leaver images
- Rank card
- and more...

# Limitations
- You can only create stuffs using the mentioned functions.
- You cannot create super-fancy things
- If you want to go deeper, you must learn canvas

# Methods
**[All The Methods are listed here](https://yuricanvas.snowflakedev.xyz/)**

# Example

```js

const yuricanvas = require("yuri-canvas");

async function create() {
    let img = await yuricanvas.trigger("./image.png");
    yuricanvas.write(img, "triggered.gif");

    let color = await yuricanvas.color("#4E5D94");
    yuricanvas.write(color, "color.png");
}

create();

```

# Discord.js Example

```js
const Discord = require("discord.js");
const client = new Discord.Client();
const yuricanvas = require("yuri-canvas");

client.on("ready", () => {
    console.log("I'm online!");
});

client.on("message", async (message) => {
    if (message.author.bot) return;
    if (message.content === "!trigger") {
        let avatar = message.author.displayAvatarURL({ dynamic: false, format: 'png' });
        let image = await yuricanvas.trigger(avatar);
        let attachment = new Discord.MessageAttachment(image, "triggered.gif");
        return message.channel.send(attachment);
    }
    if (message.content === "!delete") {
        let avatar = message.author.displayAvatarURL({ dynamic: false, format: 'png' });
        let image = await yuricanvas.delete(avatar);
        let attachment = new Discord.MessageAttachment(image, "deleted.png");
        return message.channel.send(attachment);
    }
    if (message.content === "!rank") {
        let rank = getRankSomehow();
        let image = await yuricanvas.rank({ 
            username, 
            discrim, 
            level: rank.level, 
            rank: rank.rank, 
            neededXP: rank.neededXP, 
            currentXP: rank.currentXP, 
            avatarURL: message.author.displayAvatarURL({ format: "png" }), 
            color: "white", 
            background: "https://link-to/superDuperBackground"
        });
        let attachment = new Discord.MessageAttachment(image, "rank.png");
        return message.channel.send(attachment);
    }
});

client.login("Your_Bot_Token_here");

```

# Documentation
**[https://canvacord.snowflakedev.xyz](https://canvacord.snowflakedev.xyz)**

# Preview
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/screenshot.png)

# Change My Mind
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/test/changemymind.png)

# Rank Cards
## Default
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/test/rank-default.png)

## Custom Background & Color
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/test/rank-custom-bg-and-color.png)

## Custom Background & No Overlay
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/test/rank-custom-bg-no-overlay.png)

## Custom Background
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/test/rank-custom-bg.png)

## Custom Background, Color & No Overlay
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/test/rank-custom-color-bg-no-overlay.png)

## Custom Color
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/test/rank-custom-color.png)

# Triggered
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/test/triggered.gif)

# Color
![img](https://raw.githubusercontent.com/yuri-project-ml/yuri-canvas/master/test/color.png)

> ### Read the docs for more endpoints

# Join Our Discord Server
**[discord.gg/crnmuSD](https://discord.gg/crnmuSD)**
