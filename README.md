# FFRKInspector v0.1 alpha

Please submit issues you find using the alpha version of FFRK Inspector here.

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
