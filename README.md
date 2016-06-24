A repository of macOS .mobileconfig Profiles for a myriad of system and user preferences

# THE BIG PROFILES PROJECT
(i.e. WorkGroupMgr we don't like you, be gone)

## Profile Command line management
Use /usr/bin/profiles 

-P see all profiles aggregated  
-L see only user profiles  
-D removes all profiles  
-I installs profiles  
-R removes profiles  
-s install at the next boot
-p to manage profiles from Profile Manager or pushed with Munki.


## Convert ProfileManager Profile to Proper XML
Clean up a Profile downloaded from ProfileManager from a single line to proper xml plist format
	
	plutil -convert binary1 /path/to/Profile.mobileconfig 
	plutil -convert xml1 /path/to/Profile.mobileconfig 

# MasterProfileTemplate.mobileconfig

In my struggles to understand and deploy profiles in the past few months led me to create a master template that is clear to understand and reproducible for many different system and application settings.

Containing commentary on each section this is a great way for first timers in the world of management profiles.

The MasterProfileTemplate.mobileconfig can be deployed as is by simply replacing the indicated relevant areas to what your profile is to accomplish. Save it as a .mobileconfig and deploy it. Keep the comments in place if you’d like, it works perfectly fine with them included in my testing.

This is a manual process than the very intelligently created [MCXtoProfile](https://github.com/timsutton/mcxToProfile), which is what you’ll likely need if targeting MCX settings for your .mobileconfig. This master template can be works well for .plists you have access to read and copy the keys on your environment.

## Resources
https://github.com/timsutton/mcxToProfile  
https://github.com/nmcspadden/Profiles  
http://krypted.com/mac-security/using-the-profiles-command-in-yosemite/  
http://www.amsys.co.uk/2015/02/creating-config-profiles-instead-first-boot-script/