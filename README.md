# FFRKInspector v0.1 alpha

Please submit issues you find using the alpha version of FFRK Inspector here.

Installation instructions:

1. Download [Fiddler 4](http://www.telerik.com/download/fiddler) for Windows
2. Copy FFRKInspector.dll and Newtonsoft.Json.dll to Documents\Fiddler2\Scripts
3. Run Fiddler.  You should see an FFRK Inspector tab on the right.  But wait!  You're not ready yet.
4. Configure Fiddler for [iOS](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForiOS) or [Android](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForAndroid) depending on your device.  **Note: You may need to edit the value in Tools > Fiddler Options > HTTPS > Enabled Protocols and set the string to "ssl3;tls1.2".  If you find yourself unable to browse to any websites or have degraded or no internet connectivity, check the value of this setting.**
5. If everything is working, the left hand side should start displaying traffic from your mobile device as you browse the web or play FFRK.
6. Once you find that everything is working, visit the "About" page of FFRK Inspector and enter the correct database credentials.  Press Test to test your connection, and if everything is working, press Save and restart Fiddler.
6. Play the game!  That's it!  Submit issues you find (including feedback and/or feature requests) via the [Issue Tracker](https://github.com/cppisking/ffrk-inspector/issues).  In particular, let me know which features you want me to prioritize the most.  
