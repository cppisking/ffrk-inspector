# FFRKInspector v0.1 alpha

**Having trouble?  Doesn't work?  Random question?**  Please create an [Issue](https://github.com/cppisking/ffrk-inspector/issues) on Github instead of emailing me.  That way if other people have the same issue, I won't have to answer the same question many times.

Installation instructions:

1. Download [Fiddler 4](http://www.telerik.com/download/fiddler) for Windows
2. Install [MySQL Connector for .NET](https://dev.mysql.com/downloads/connector/net/)
3. Copy FFRKInspector.dll and Newtonsoft.Json.dll from the [Releases](https://github.com/cppisking/ffrk-inspector/releases) page to Documents\Fiddler2\Scripts
4. Run Fiddler.  You should see an FFRK Inspector tab on the right.  But wait!  You're not ready yet.
5. Configure Fiddler for [iOS](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForiOS) or [Android](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForAndroid) depending on your device.  **Note: You may need to edit the value in Tools > Fiddler Options > HTTPS > Enabled Protocols and set the string to "ssl3;tls1.2".  If you find yourself unable to browse to any websites or have degraded or no internet connectivity, check the value of this setting.**
6. If everything is working, the left hand side should start displaying traffic from your mobile device as you browse the web or play FFRK.
7. Once you find that everything is working, visit the "About" page of FFRK Inspector and enter the correct database credentials.
  1. **Host**: ffrk-test.ckamoyrtavob.us-west-2.rds.amazonaws.com
  2. **User**: ffrki-alpha
  3. **Password**: e6v8uaQ3vhdYPSSgaGWU
  4. **Database Name**: ffrki-alpha
8. Press Test to test your connection, and if everything is working, press Save and restart Fiddler.
9. Play the game!  That's it!  Submit issues you find (including feedback and/or feature requests) via the [Issue Tracker](https://github.com/cppisking/ffrk-inspector/issues).  In particular, let me know which features you want me to prioritize the most.  

**FAQ (more things will be added to this list in time):**

Q: *I closed the app in the middle of a battle and it didn't update the "All Drops for this Dungeon" view.*

A: It only updates when you win, lose, or flee a battle, to make sure that each server roll is only committed to the database a single time.  

Q: *Is there any way to see the drops for a dungeon even when I'm not in that dungeon?  So I can find *everywhere* that drops a particular item and find the most efficient farming place?*

A: Not yet, but I expect that will be the next thing I work on.  It will probably be in the "Item Search" tab of the Inspector.
