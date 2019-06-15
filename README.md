A repository of macOS .mobileconfig Profiles for a myriad of system and user preferences

# THE BIG PROFILES PROJECT
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

## Validate a plist or mobile config 
Checks all the opening and closing dict, arrays, etc and other formatting errors in plists.

	plutil -lint /path/to/Profile.plist

# MasterProfileTemplate.mobileconfig

In my struggles to understand and deploy profiles in the past few months led me to create a master template that is clear to understand and reproducible for many different system and application settings.

Containing commentary on each section this is a great way for first timers in the world of management profiles.

https://github.com/rodchristiansen/Profiles/blob/master/MasterProfileTemplate.mobileconfig

The MasterProfileTemplate.mobileconfig can be deployed as is by simply replacing the indicated relevant areas to what your profile is to accomplish. Save it as a .mobileconfig and deploy it. Keep the comments in place if you’d like, it works perfectly fine with them included.

All of our profiles come from this master standard template. It's an artisanal process that we will probably automate more in the future.

I'll point you to the excellent ProfileCreator as an option: https://github.com/erikberglund/ProfileCreator
