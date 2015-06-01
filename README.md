# FFRKInspector v0.1 alpha

**Having trouble?  Doesn't work?  Random question?**  First check the FAQ and Troubleshooting section below, and then if it still doesn't work, create an [Issue](https://github.com/cppisking/ffrk-inspector/issues) on Github instead of emailing me.  That way if other people have the same issue, solutions will be easier for others to find.

Installation instructions:

1. Download [Fiddler 4](http://www.telerik.com/download/fiddler) for Windows
2. Install [MySQL Connector for .NET](https://dev.mysql.com/downloads/connector/net/)
3. Copy FFRKInspector.dll, FFRKInspector.pdb, and Newtonsoft.Json.dll from the [Latest Release](https://github.com/cppisking/ffrk-inspector/releases/latest) page to Documents\Fiddler2\Scripts (Recommended to run Fiddler and then close before doing this step.  It will create this folder for you).
4. Run Fiddler.  You should see an FFRK Inspector tab on the right.  But wait!  You're not ready yet.

**Configuring Fiddler to capture traffic from your phone.**

*Using Bluestacks?  These steps may not be necessary!  If you have problems though, create an
[Issue](https://github.com/cppisking/ffrk-inspector/issues) and hopefully I or someone else can help.*

1. Configure Fiddler for [iOS](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForiOS) or [Android](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForAndroid) depending on your device.
2. Configure Fiddler HTTPS options as shown in the following image.
<img src="http://i.imgur.com/xYL5x3v.jpg"/>
More information about these steps can be found on the corresponding platform specific configuration page linked in step 1.

6. If everything is working, the left hand side should start displaying traffic from your mobile device as you browse the web or play FFRK (Note: If you use Chrome on iOS, sites requiring https will not work.  There is no workaround for this, it is a limitation of iOS -- not a limitation of Chrome -- and there is no solution except use Safari or disable the proxy).

7. Once you find that everything is working, visit the "About" page of FFRK Inspector and enter the following credentials.
  1. **Host**: ffrk-test.ckamoyrtavob.us-west-2.rds.amazonaws.com
  2. **User**: ffrki-user
  3. **Password**: qUm1FyGjU8USclhKY4gF
  4. **Database Name**: ffrki
8. Press Test to test your connection, and if everything is working, press Save and restart Fiddler.
9. Play the game!  That's it!  Submit issues you find (including feedback and/or feature requests) via the [Issue Tracker](https://github.com/cppisking/ffrk-inspector/issues).  In particular, let me know which features you want me to prioritize the most.  

**FAQ (more things will be added to this list in time):**

Q: *I can see my drops and it appears to be working, but how can I see others' drops?  How do I know they can see mine?*

A: First, look at the bottom for "Status: Connected" or "Status: Disconnected".  If it says Connected then you have an active connection to the database.  Try searching for some items on the Item Search tab.

Q: *I closed the app in the middle of a battle and it didn't update the "All Drops for this Dungeon" view.*

A: It only updates when you win, lose, or flee a battle (as well as a couple other edge cases), in order to make sure that each server roll is only committed to the database a single time.  

Q: *Is there any way to see the drops for a dungeon even when I'm not in that dungeon?  So I can find *everywhere* that drops a particular item and find the most efficient farming place?*

A: Check the Item Search tab.

Q: *The inventory tab is empty, even though I was looking at the tab when I clicked "Party"*

A: Close and restart FFRK, then try again.  This is a limitation of FFRK Inspector currently.  I plan to take steps to make this less annoying in the future.

Q: Any plans to bring this to Mac or Linux?

A: Not at the moment.  Fiddler (which is the proxy on which this is built) as well as my own Fiddler extension are written in C#, which does not run natively on any platform other than Windows.  There is a thing called Mono which can run C# apps on these platforms, but it has some limitations, and it's not clear whether Fiddler or my extension will fall outside the scope of what is possible under Mono.  However, I expect it to not work.  Sorry!

Q: What about bringing a read-only view of the database to the web?  Or to mobile?

A: Mobile is a possibility which I'm actively considering.  I want to see how well this is received first, and weigh whether or not I'm willing to put the time into writing a mobile app.  This has already exploded into something way bigger and more involved than I originally anticipated, so we'll see :)

**Troubleshooting**

Q: *I can play the game, and I see some stuff in Fiddler, but there's nothing in the UI and it looks like it's not working.*

A: You probably didn't set up your SSL certificate correctly.  There's a lot of steps and it's easy to miss one.  See [here](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForiOS) for iOS instructions and [here](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForAndroid) for Android instructions.  If all you see on the left hand side of Fiddler is "Tunneling to <url>" then Fiddler isn't able to decrypt any of the requests due to a problem with your certificate.  Try opening Safari (not Chrome) on iOS, or any browser on Android.  Then browse to www.google.com.  If the page loads, then FFRK should be working.


