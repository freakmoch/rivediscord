#riveMsg()
This version includes a cute little feature - the `riveMsg(trigger, type)` function. This lets you call from a rivescript trigger (the little + sign messages) for anything -- not just for chatting.

## Usage

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

## Types

You can create different types of riveMsg() calls as you please. The code has a second preset (1) where if you type `riveMsg("hello",1)`, a sakura emoji will appear next to the message automatically when ran.

If you're savvy with JavaScript, you can add your own types to the function (or even improve it, since I'm a newbie to JS myself) 
