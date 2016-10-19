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
3.  Pull down your **Token** and paste it into line 18 / the `token: 'tokenhere'` line and SAVE.
4.  Open up your terminal in the `bot` folder. If you're using windows, cd to `%HOMEPATH%/Desktop/bot`
5.  Install the discordie dependency by typing `npm install --save discordie`
6.  Install the rivescript dependency by typing `npm install --save discordie`

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

## Errors

- **Bot never says 'Connected as [Bot Name]'** Your token is wrong! Generate a new one and paste it in to `main.js`
- **Triggers cannot contain symbols:** Rivescript Error! Shutdown your bot and fix this.
