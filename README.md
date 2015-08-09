# FFRKInspector

FFRK Inspector is a tool used to assist you in farming orbs or items.  It works by acting as a proxy between your device and the game's server, so that it can see various events in real time as they happen.  It is backed by a centralized database which is used to crowdsource information about drop rates.  In short, everyone who plays the game while connected to FFRK Inspector will automatically contribute statistics about their drops to a single master database.  You can then query the database to find out, for example, where the most efficient farming spot is for a particular item.

Note: Due to being built using C# and the .NET Framework, FFRK Inspector is currently only supported for Windows.  If you can get it working under Mono using Mac or Linux, that's great!  I will accept contributions for unofficial guides for getting everything installed and working under those platforms, should someone get it working and feel like contributing.  But please note that I can only provide support for FFRK Inspector running on Windows.


**Having trouble?  Doesn't work?  Random question?**  First check the FAQ and Troubleshooting section below, and then if it still doesn't work, create an [Issue](https://github.com/cppisking/ffrk-inspector/issues) on Github instead of emailing me.  That way if other people have the same issue, solutions will be easier for others to find.

## Installation instructions:

#### Installing and configuring Fiddler
1. Download [Fiddler 4](http://www.telerik.com/download/fiddler) for Windows.
2. Run the installer.  You can accept the default options.

     ![GitHub Logo](/Images/Documentation/fiddler1.png)
     ![GitHub Logo](/Images/Documentation/fiddler2.png)
     ![GitHub Logo](/Images/Documentation/fiddler3.png)
3. Start Fiddler, for just FFRK purposes you can click ‘Cancel’ on this dialog box. We don’t need to capture traffic from Universal/Metro apps.

     ![GitHub Logo](/Images/Documentation/fiddler4.png)
4. Once Fiddler is open, go to Tools -> Fiddler Options.

     ![GitHub Logo](/Images/Documentation/fiddler5.png)
5. Go to the HTTPS tab and check the box for Decrypt HTTPS traffic. A dialog box will pop up asking if you want your computer to trust the Fiddler generated interception certificate. You can click ‘No’, as we’re not interested in intercepting traffic on the PC.

     ![GitHub Logo](/Images/Documentation/fiddler6.png)

   You can set it to decrypt HTTPS traffic “…from remote clients only”.
     ![GitHub Logo](/Images/Documentation/fiddler7.png)

6. Next go to the Connections tab, and check the box for “Allow remote computers to connect”, and you can also uncheck “Act as system proxy on startup”, as again, we’re not interested in seeing traffic from the local PC. Hit OK after you’re done, that completes Fiddler configuration.
     
     ![GitHub Logo](/Images/Documentation/fiddler8.png)

#### Installing MySQL Connector
1. Download the [MySQL Connector for .NET](https://dev.mysql.com/downloads/connector/net/)
2. Run the installer. You can pick the “Typical” option and click through the rest.

     ![GitHub Logo](/Images/Documentation/mysql1.png)
     ![GitHub Logo](/Images/Documentation/mysql2.png)
     ![GitHub Logo](/Images/Documentation/mysql3.png)
     ![GitHub Logo](/Images/Documentation/mysql4.png)

#### Configuring FFRK Inspector Add-In

1. Download the latest release from https://github.com/cppisking/ffrk-inspector/releases. You'll need the following files: FFRKInspector.dll, FFRKInspector.pdb, HtmlAgilityPack.dll, and Newtonsoft.Json.dll.
2. Save each file in to the Fiddler2\Scripts folder in your My Documents.
   
     ![GitHub Logo](/Images/Documentation/inspector1.png)
3. Start Fiddler (restart it if it was open), and you should have a new tab show up on the right, FFRK Inspector.

     ![GitHub Logo](/Images/Documentation/inspector2.png)
4. Go the About tab with FFRK Inspector and copy and paste the login info below. Hit the Test button and make sure you get a success message and restart Fiddler.
  1. **Host**: ffrk-test.ckamoyrtavob.us-west-2.rds.amazonaws.com
  2. **User**: ffrki-user
  3. **Password**: qUm1FyGjU8USclhKY4gF
  4. **Database Name**: ffrki

     ![GitHub Logo](/Images/Documentation/inspector3.png)

5. When Fiddler starts up it should say “Status: Connected” in the lower left of the FFRK tab. That’s it for the FFRK configuration.

### Setting up your device

#### Android (Generic)

This was tested on Nexus 5 and 7 devices running Android 5.0.2 and an NVIDIA Shield Tablet running Android 5.1.1.

1. Go to Wi-Fi settings and long press on your SSID. Click on “Modify network”

     ![GitHub Logo](/Images/Documentation/android_wifi.png)
2. Check the “Advanced options” box and fill in the IP address of the computer which you installed Fiddler on, and set the port to 8888. Make sure to add 127.0.0.1 to the “Bypass proxy for” setting or the game will not load completely. You can find your computer’s IP address by opening a cmd prompt and running the command: ipconfig

     ![GitHub Logo](/Images/Documentation/android_wifi_detail.png)
     ![GitHub Logo](/Images/Documentation/ipconfig.png)
3. Once that is set, open Chrome and browse to: http://<your IP address>:8888, so in my case, it’s http://192.168.1.97:8888. You should get this page served up by the Fiddler app.

     ![GitHub Logo](/Images/Documentation/android_chrome_fiddler.png)
4. Click on the “FiddlerRoot certificate” link at the bottom of the page.  Type in a name for the certificate, I named it “Fiddler”. Hit OK.

     ![GitHub Logo](/Images/Documentation/android_cert_name.png)
5. If you don’t already have a PIN set on your device, you will need to set one.

     ![GitHub Logo](/Images/Documentation/android_cert_security.png)

6. Once that is set, you will get this warning. Clicking on the “CHECK TRUSTED CREDENTIALS” link will show you that you have the Fiddler root certificate installed. You will permanently have the "!" triangle in your notifications reminding you that your traffic can potentially be sniffed. At this point you should be able to open FFRK on your device and as long as Fiddler is running it should load up and you’ll start to see data being populated in the FFRK Inspector tabs as you move in and out of dungeons.

     ![GitHub Logo](/Images/Documentation/android_trusted_credentials.png)
     ![GitHub Logo](/Images/Documentation/android_trusted_credentials_list.png)

#### Apple/iOS

This was tested on an iPad Mini 2 running iOS 8.3.

1. Go to Settings, Wi-Fi and click on the ‘i’ with the blue circle around it.

     ![GitHub Logo](/Images/Documentation/iOS_wifi.png)
2. Near the bottom under “HTTP Proxy”, select “Manual” and fill in the IP address of the computer you installed Fiddler on, and set the port to 8888. If you need to find your computer’s IP address, you can do so by opening a cmd prompt and running the command: ipconfig

     ![GitHub Logo](/Images/Documentation/iOS_wifi_detail.png)
     ![GitHub Logo](/Images/Documentation/ipconfig.png)
3. Open Safari and browse to: http://<your IP address>:8888, so in my case, it’s http://192.168.1.97:8888.  Click on the “FiddlerRoot certificate” link at the bottom of the page.  Type in a name for the certificate, I named it “Fiddler”. Hit OK.

     ![GitHub Logo](/Images/Documentation/iOS_safari_fiddler.png)
4. You’ll be prompted to install the Fiddler root certificate. Go ahead and click “Install” in the upper right.

     ![GitHub Logo](/Images/Documentation/iOS_install_cert.png)

   You’ll get an additional warning saying that the certificate is unverified, click “Install” again.
   
     ![GitHub Logo](/Images/Documentation/iOS_cert_warning.png)
     
   And click "Install" once more.
   
     ![GitHub Logo](/Images/Documentation/iOS_cert_confirm.png)
     
   At this point you should be able to open FFRK on your device and as long as Fiddler is running it should load up and you’ll start to see data being populated in the FFRK Inspector tabs as you move in and out of dungeons.
   
----


**Configuring Fiddler to capture traffic from your phone.**

**Bluestacks Users:**  FFRK Inspector may not work.  You're welcome to try, but so far people have reported difficulty configuring Bluestacks to use an HTTP Proxy

**Android Users:**  Try the steps below, but if they don't work, see [this thread](http://www.reddit.com/r/FFRecordKeeper/comments/35x6nq/introducing_ffrk_inspector_and_looking_for_alpha/cr9gz5n).  Android configuration is complicated by a number of factors, and there does not seem to be a single universal solution for all Android users.   **Note that Android users will need to add a bypass of 127.0.0.1 on their wifi proxy**

1. Configure Fiddler for [iOS](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForiOS) or [Android](http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/ConfigureForAndroid) depending on your device.
2. Configure Fiddler HTTPS options as shown in the following image.  <img src="http://i.imgur.com/xYL5x3v.jpg"/>

More information can be found on the corresponding platform specific configuration page linked in step 1.

(Update: The certificate maker plugin is for iOS, not Android.  Ignore that part of the screenshot if you're on Android).

3. If everything is working, the left hand side should start displaying traffic from your mobile device as you browse the web or play FFRK (Note: If you use Chrome on iOS, sites requiring https will not work.  There is no workaround for this, it is a limitation of iOS -- not a limitation of Chrome -- and there is no solution except use Safari or disable the proxy).

**Connecting to the Database**

Visit the "About" page of FFRK Inspector and enter the following credentials.
  1. **Host**: ffrk-test.ckamoyrtavob.us-west-2.rds.amazonaws.com
  2. **User**: ffrki-user
  3. **Password**: qUm1FyGjU8USclhKY4gF
  4. **Database Name**: ffrki
5. Press Test to test your connection, and if everything is working, press Save and restart Fiddler.
6. Play the game!  That's it!  Submit issues you find (including feedback and/or feature requests) via the [Issue Tracker](https://github.com/cppisking/ffrk-inspector/issues).  In particular, let me know which features you want me to prioritize the most.  

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


