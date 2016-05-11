A repository of Mac OS .mobileconfig Profiles for a myriad of system and user preferences

THE BIG PROFILES PROJECT
(i.e. WorkGroupMgr we don't like you, be gone)

***********************************
* Profile Command line management *
***********************************
Use /usr/bin/profiles 

-P see all profiles aggregated
-L see only user profiles
-D removes all profiles
-I installs profiles
-R removes profiles

There is a nifty new feature in the profiles command in Yosemite where you can configure profiles to install at the next boot, rather than immediately. Use the -s to define a startup profile and take note that if it fails, the profile will attempt to install at each subsequent reboot until installed. To use the command, simply add a -s then the -F for the profile and the -f to automatically confirm, as follows (and I like to throw in a -v usually for good measure):

/usr/bin/profiles -s -F /Profiles/SuperAwesome.mobileconfig -f -v


*************************************************
* Convert ProfileManager Profile to Proper XML *
*************************************************
Clean up a Profile downloaded from ProfileManager from a single line to proper xml plist format
	
	plutil -convert binary1 /path/to/Profile.mobileconfig 
	plutil -convert xml1 /path/to/Profile.mobileconfig 


************************************
* Profiles Locations and Resources *
************************************
Text file documenting management profiles created by MacTechs. Storage location for Profiles is the /Volumes/DeploymentRepository/Profiles in Pluto and mirrored in Proteus for redundancy.
* Resources *

https://github.com/timsutton/mcxToProfile
https://github.com/nmcspadden/Profiles
http://krypted.com/mac-security/using-the-profiles-command-in-yosemite/
http://www.amsys.co.uk/2015/02/creating-config-profiles-instead-first-boot-script/


*************************
* General Configuration *
*************************

<key>PayloadDescription</key> and <key>PayloadDisplayName</key> 
I have been keeping the same, as short as possible and camel backed.

<key>PayloadIdentifier</key>
Naming convention 
ca.ecuad.mactech.profile.PROFILENAME 

<key>PayloadScope</key>	
<string>User or System</string>
important key that determines if profile is only for this user or if its system wide

<key>PayloadRemovalDisallowed</key>
Determines if admin password is needed for removal

<key>PayloadVersion</key>
Version coupled with the identifier key Munki is able to version things properly for installs and uninstalls

Example profile to keep student account wallpaper always the same *no matter what* when used together with Outset as a first-login package things get very interesting.
