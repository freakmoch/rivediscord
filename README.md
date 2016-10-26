# rivediscord

A discord bot that uses rivescript to process messages

I don't know if anyones already made a repository for this. But heres mine.

## Requirements

- Latest Node.js installed
- Discord, of course.
- Basic knowlege how to use cmd/a terminal
- Basic knowledge of Javascript and Rivescript

## Links

- Node.js: https://nodejs.org/en/
- Discordie docs: https://qeled.github.io/discordie/
- Rivescript docs: https://www.rivescript.com/docs/tutorial
- rivescript-js docs: https://github.com/aichaos/rivescript-js/tree/master/docs

## Setup

I suck at explaining, but heres a rundown how to get this bot working. I am going to make this *extremely* simple, because i recfuse to assume you know **anything** other than the requirements.

### 1. Setting up a bot

1.  Go to https://discordapp.com/developers/applications/me in your browser
2.  Create a new app & name it whatever you want. Click OK
3.  Create a bot user (It should be at the very top) and confirm.
4.  Copy the clientID and Token somewhere safe

### 2. Setting up your bot folder

1.  Create a bot folder on your desktop. just `/bot/` is fine
2.  copy in the `package.json`, `main.js`, and **your** `.rive` file to the `/bot/` directory
    (If you don't have one, nab the sample off the rivescript site.)
3.  Open `main.js` and admire its beauty.
3.  Pull down your **Token** and paste it into *line 18* / the `token: 'tokenhere'` line.
5.  Go to *line 24* and replace `yourrivefilehere.rive` with your actual rive file. Save the file
6.  Open up your terminal in the `bot` folder. If you're using windows, cd to `%HOMEPATH%/Desktop/bot`
7.  Install the discordie dependency by typing `npm install --save discordie`
8.  Install the rivescript dependency by typing `npm install --save discordie`

### 3. Add your bot to your server

1.  Pull down your **Client ID**
2.  Paste the client id into this url: `https://discordapp.com/oauth2/authorize?&client_id=CLIENTIDHERE&scope=bot`
3.  Visit the URL and add the bot into your server. You **MUST** have admin privileges to add a bot to any server.
4.  Celebrate.

### 4. Running your bot

1.  Open up your terminal in the `bot` folder. If you're using windows, cd to %HOMEPATH%/Desktop/bot
2.  Type `npm run test` in to the terminal 
3.  If no errors pop up, you can begin talking to your bot!

### 5. Shutting down your bot

- For Linux, press `ctrl + Z` once.
- For Windows, press `ctrl + C` twice

After everything is running correctly, you can modify `main.js` to your liking. I commented it enough that it should be easy to see what does what!

## riveMsg()

This version includes a cute little feature - the `riveMsg(trigger, type)` function. This lets you call from a rivescript trigger (the little + sign messages) for anything -- not just for chatting.

### Usage

Say your rive file has this written in it:

```
+ hello
- Hello World!
```

Calling `riveMsg("hello", 0)` will process the trigger as a local user and the bot will message `Hello World!` to the server automatically. 

You can also write the bots commands in Rivescript too; Example: when someone types `!help`, you can translate it to a rive trigger as `+ botcommand help`, then have the message write from rive itself.

So you'd have a script in main.js like this:
```
if(usrSentMsg == "!help") {  
		riveMsg("botcommand help", 0);
     	}
```

and have your rive file include this:
```
+ botcommand help
- My commands are !help, !ping, !bleep, !boom, !bam
^ If you'd like to chat, just call my name!
```

I wrote the function solely to minimize typing and unclutter the code, since writing the entire `e.message.channel.sendMessage(talkback.reply("local-user", "hello"));` can get confusing really quick, and having all the bots text organized in one or two rive files (ex. `chat.rive` and `commands.rive`) is much, much easier and more organized.

### Types

You can create different types of riveMsg() calls as you please. The code has a second preset (1) where if you type `riveMsg("hello",1)`, a sakura emoji will appear next to the message automatically when ran.

If you're savvy with JavaScript, you can add your own types to the function (or even improve it, since I'm a newbie to JS myself) 

## Errors

- **Bot never says 'Connected as [Bot Name]'** Your token is wrong! Generate a new one and paste it in to `main.js`
- **Triggers cannot contain symbols:** Rivescript Error! Shutdown your bot and fix this.
