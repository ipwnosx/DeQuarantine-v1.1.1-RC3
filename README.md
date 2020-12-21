# DeQuarantine-v1.1.1-RC3
DeQuarantine is a tool to remove the quarantine extended attribute (XA) from any file or application, and to manage your Gatekeeper settings.  General note: always dequarantine downloaded archives and DMGs before expanding or mounting them, because the quarantine XA will usually be inherited by the contained files.


## FEATURES:
● Open any downloaded file, e.g. a zip or DMG, or an application with DeQuarantine, and remove its quarantine extended attribute (XA)
● If you do not dequarantine cracked applications, they might not launch, and macOS will tell you e.g. that the “application is damaged”
● Besides removing the quarantine XA, DeQuarantine will also add Gatekeeper exemptions for any targeted application bundle under the spctl label deQ (does not apply if the application is not quarantined)
● If launched by itself, DeQuarantine will let you manage your macOS Gatekeeper settings, i.e. disable and re-enable Gatekeeper, set to App-Store-only etc.
◦ Note: the recommended setting is App Store and identified developers
◦ Note: there is absolutely no need to disable Gatekeeper; instead please only dequarantine downloaded files and misbehaving applications, unless you like the added security risk of a disabled Gatekeeper
◦ Note: when switching to the setting App Store (which is usually not necessary), DeQuarantine will not touch any of your previous GK rules and exceptions, and in the GUI Security & Privacy preference pane in System Preferences, Gatekeeper might still be shown as set to “App Store and identified developers” (this needs further research)
● Important general note: there is one big Catch-22, because DeQuarantine is an application, and an application is not allowed to open another application or file, if the latter app or file is unsigned or from an unidentified developer, or if the code-signing integrity has been compromised by a crack. For DeQuarantine to open such an application or file, the target app/file would need to be dequarantined first, which is not possible, because DeQuarantine is not allowed to open it. ;) This means that you must install the DeQuarantine Finder QuickAction workflow, because the workflow will call the Platypus script directly. If you have disabled Spotlight (which you shouldn’t do), this will not work, because the workflow will not be able to find the DeQuarantine app, and then you need to use the shell script instead, and build your own QuickAction on top of it.
◦ Related note: in certain file managers other than Finder, e.g. Nimble Commander, you need to enter the path to the nested script – e.g. /Applications/DeQuarantine.app/Contents/Resources/script – if you want to add DeQuarantine as an integrated file manager tool
● RC note: until now everything has been working fine on my system, but I hope you’ll report issues or bugs. Thank you. If you run into problems, execute the shell script directly in your terminal emulator (e.g. macOS Terminal or iTerm), and look at the output. DeQuarantine will remain in release candidate status for at least a couple of weeks.
● Why “dequarantine”? Because “unquarantine” sounds stupid.
Installation instructions:

Manually dequarantine the downloaded DMG in your terminal emulator, e.g. macOS Terminal or iTerm—example:
xattr -d ~/Downloads/DeQuarantine_v1.1.1RC3.dmg
—then mount the DMG volume

Copy DeQuarantine.app from the mounted DMG volume into one of your applications paths; recommended: ~/Applications/Utilities/


If you are using macOS Finder or a similar application with Services support as your main file manager, double-click the DeQuarantine workflow: a window titled Quick Action Installer will appear asking you if you want to install it; click Install. You can assign a keyboard shortcut to the Quick Action in System Preferences > Keyboard > Shortcuts > Services > Files and Folders > DeQuarantine

On Mojave please allow DeQuarantine to control System Events; this is necessary for GUI prompts to work via AppleScript

## PICTURE EXAMPLES:
https://i.ibb.co/B3kjXfX/5ac9NTK.jpg
https://i.ibb.co/LShYKxn/P3oytDb.jpg
https://i.ibb.co/kcJXWgV/S32pkOv.jpg