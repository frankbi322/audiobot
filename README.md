Welcome!

## What is Audiobot?

Audiobot is an audio feedback bot for Slack.  Slack Audiobot is written in node.js and plays MP3 files from its /sound directory based on queues from Slack users.


## How to install Audiobot
1. Grab the repo and run npm install. This will install all of the dependencies Audiobot requires.
2. Add a bot integration in Slack [here](https://slack.com/services/new/bot)
3. Add your bot's API key to config.js
4. Run `node audiobot.js` from the command line
5. Invite your brand new bot into the channels you'd like it to watch.
6. To use scheduling audio commands, make sure that the official slack bot is also in the channel you want to use these in.

## Commands
Here's a couple commands you might like to try:
* `play bell` - this will play the bell noise (comes with this package)
* `@BOTNAME help` - get a list of commands you can use with your bot (replace BOTNAME with your bot's name, obviously)
* `@BOTNAME list` - get a list of valid sound files. If you want more, just dump them in the sounds folder
* `@BOTNAME stop` - stop the bot listening to requests for sounds
* `@BOTNAME start` - start the bot listening to requests for sounds  (on by default)

## Setting up Audio Cues
The core functionality of this bot is to play audio files whenever a message is entered that meets certain criteria.

For example, using Javascript's indexOf function, we can set up basic audio cues if the last message indicates excitement (if it contains "!!!") or confusion ("???") or even sadness (":(").

You can import new mp3 files or record voice clips as well. Try it out!


## Clock-based events
To create scheduled audio cues at certain times of the day/week, first make sure both Audio-Bot and the official slack bot are both in the channel you want to use these in.

Next, set a reminder with slack-bot. For example, this bot plays a message at 9am every weekday. To replicate this, type the following command:
/remind @channel "good morning everyone" at 9am every weekday

Slack bot will message the channel, and the message's contents will trigger audio-bot to play the corresponding audio file.
