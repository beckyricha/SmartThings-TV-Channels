# SmartThings-TV-Channels - only works if you have a hub

Allows easy setup of TV channels, if you already have a smartthings device that can send numbers 0-9 to your channel changing device (TV, STB, HTPC, etc).  This can be any kind of device if it operates quickly enough, but for this first version, those keys need to operate like switches (to operate them you send it an "on" command).  Once the kinks of timing are worked out I can add other tytpes of devices but may need input from their owners about what kind of commands it accepts.  This would allow Alexa and Google home to easily send TV channels using non-switch device types.  This is a first attempt, and likely will have issues depending on your device timing. For me, this does work with the RM Bridge LAN (<a href='https://beckyricha.github.io/Broadlink-RM-SmartThings-Alexa.html'>my other repo</a>).  For users of that setup, this should help avoid the tedious programming associated with trying to set up channels with the "multikeys" device (my v1 attempt at TV channels).  

Here's a quick overview.  I'll add more detail as it gets used and I see what questions people have.

## Install the apps
If you know how to automaatically update to your smartthings account from a repo, this is set up so that should work.  Otherwise, just follow these steps:

1. Install the device handler, "dummyswitch" here's how:
  * go to https://graph.api.smartthings.com/ and create or login to your account
  * go to my Device Handlers and select Create new device handler
  * click "from code"
  * paste the contents of the file <a href='https://github.com/beckyricha/SmartThings-TV-Channels/blob/master/devicetypes/beckyricha/dummyswitch.src/dummyswitch.groovy'>dummyswitch.groovy</a> into the box and save
  * click "publish" and then "for me"

2. Install the SmartApp TV Channel Creator - same as steps above, except that you go to "my smart apps" instead of "my device handlers" to create a new Smart App.  The code comes from my <a href='https://github.com/beckyricha/SmartThings-TV-Channels/tree/master/smartapps/beckyricha/tv-channel-creator.src'>tv-channel-creator.src</a> file.

3.  Install the SmartApp TV Channel Handler the same wway, using the code in the <a href='https://github.com/beckyricha/SmartThings-TV-Channels/tree/master/smartapps/beckyricha/tv-channel-handler.src'>tv-channel-handler.src</a> file.

## Set up your channels. Take steps in this order:
1. Make sure you have separate devices set up for the numbers 0-9.  This can be any type of device and can be called whatever you want. (to use Broadlink, it has to be set up and names so that will work).  Make sure these all work on their own before trying to use them through an app.

2. Install the SmartApp called TV Channel Creator.  Use your mobile, as SmartApps don't work well in the online simulator. Run it (asks for only the channel name as you would want to speak it for echo or google home) and repeat for as many channels as you want to add.  You can go back and add more later if you want to test first, but you need at least one before going to the next step. You can also add the same channel number with different names, for instance if there is more than one common way to refer to a channel.  

3. Install and run the SmartApp called TV Channel Handler.  This is where you will tell the app which devices represent 0-9, and identify the channels you set up as "dummy devices" using the other app.  I may be able to streamline this so it is selected when you make it, but that's a future feature after the functionality for enough people is confirmed.

4. If you want to add channels, use the creator app again, and then re-run the handler.  To edit channels, right now you have to delete and recreate the device.  I will add an editor app later, again after the basic app is confirmed working/useful.

## Try it out
You should be able to discover your new channel devices with Alexa or Google Home, or access them in your ST app.  Play around, and use issues to reeport what it does.  Also let mee know what works, please, so I don't "fix" it for one person and break it for others.

Have fun!
