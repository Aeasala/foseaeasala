Fallout Script Extender v1.3 beta 2
by Ian Patterson, Stephen Abel and Paul Connelly
(ianpatt, behippo and scruggsywuggsy the ferret)

The Fallout Script Extender, or FOSE for short, is a modder's resource that expands the scripting capabilities of Fallout 3. It does so without modifying the Fallout3.exe or the G.E.C.K. files on disk, so there are no permanent side effects.

Contributions from: Timeslip, Elminster EU

Compatibility:

FOSE supports these versions of Fallout 3 (from either a retail DVD or Steam):
- 1.0.0.15
- 1.1.0.35
- 1.4.0.6 (original release)
- 1.4.0.6 (alternate release, found on steam and some European patches)
- 1.5.0.22
- 1.6.0.3
- 1.7.0.3 (original and german no-gore)

FOSE is compatible with the 1.1.0.36 and 1.5.0.19 G.E.C.K.

Incompatibilities:
* FOSE is not compatible with the original, unpatched DVD or Steam version. Please patch to a newer version.

* FOSE is not compatible with the Direct2Drive (D2D) or the Russian version of Fallout 3 protected by StarForce. FOSE will never be compatible with these versions, as they are encrypted and it would be illegal to break the encryption. 

* FOSE is currently incompatible with Windows Live, so when running via fose_loader.exe, Live will be disabled. Live functions as an anti-cheat mechanism, so it disables itself if it detects any in-memory modifications to the executable, despite the fact that Fallout has no multiplayer component. Since Live cannot tell the difference between the modifications we make and the modifications a cheating program would make, we will probably never be directly compatible. To download DLC and updates, simply launch Fallout normally. Live stores DLC and save files in a separate folder when active, so some things may need to be moved around - see the official Fallout forums for more information.

This initial release adds 189 new scripting functions including:
- basic input functions based on DX scancodes
- basic form list functions
- debugging console functions
- various weapon and inventory item Get and Set functions
- script versions of several console functions
- Looping functions (Label, Goto)
- GetCrosshairRef
- get and set game setting and INI functions
- loaded mod informtion functions
- reference walking functions
- Basic UI Functions (GetUIFloat, SetUIFloat, SetUIString)
- basic math and bit flag functions
- GetGameRestarted, GetGameLoaded
- temporary base form cloning functions

[ Installation ]

1. Copy the .dll files and fose_loader.exe to your Fallout 3 directory. This is usually in your Program Files folder, and should contain files called Fallout3.exe, FalloutLauncher.exe and the G.E.C.K. (if installed).

2. Launch Fallout by running fose_loader.exe from the Fallout3 directory.

If you use a desktop shortcut to launch Fallout 3 normally, just update the shortcut to point to fose_loader.exe instead of Fallout3.exe or FalloutLauncher.exe.

Scripts written with these new commands must be created via the G.E.C.K. after it is launched via fose_loader.  Open a command prompt window, navigate to your Fallout 3 install direcory, and type "fose_loader -editor". Alternately you can create a shortcut to fose_loader.exe, open the properties window and add "-editor" to the Target field. The normal editor can open plugins with these extended scripts, but it cannot recompile them and will give errors if you try.

[ Suggestions for Modders ]

If your mod requires FOSE, please provide a link to the main FOSE website <http://fose.silverlock.org/> instead of packaging it with your mod install. Future versions of FOSE will be backwards compatibile, so including a potentially old version can cause confusion and/or break other mods which require newer versions. If you are making a large mod with an installer, inclusion of a specific version of FOSE is OK, but please check the file versions of the FOSE files before overwriting them, and only replace earlier versions.

When your mod loads, use the command GetFOSEVersion to make sure a compatible version of FOSE is installed. In general, make sure you are testing for any version later than the minimum version you support, as each update to FOSE will have a higher version number. Something like:

if GetFOSEVersion < 5
   MessageBox "This mod requires a newer version of FOSE."
endif

[ Troubleshooting / FAQ ]

* My savegames are missing!
 - Since Live is incompatible with any mod that modifies the Fallout runtime in memory, profiles are disabled as well. To restore them, go to your My Documents folder, open My Games, open Fallout3, then open Saves. There should be a folder inside for each profile - just move the contents out in to the Saves folder and relaunch Fallout. To access the savegames when using Live, you will need to either sign out of your current profile or move the files back.

* Fallout 3 doesn't launch after running fose_loader.exe:
 - make sure you've copied the FOSE files to your Fallout 3 directory.  That folder should also contain Fallout3.exe.
 - check the file fose_loader.log in your Fallout 3 folder for errors.

* fose_loder.log tells me it couldn't find a checksum:
 - you may have a version of Fallout 3 that isn't supported.  We test on the English DVD version of Fallout.  Localized versions with different executables or different patches may not work.  If there's enough legitimate demand for it, we can add support for other versions in the future.
 - Your Fallout 3 install may be corrupt.  Hacks or no-cd patches may also change the checksum of the game, making it impossible to detect the installed version.

* FOSE doesn't launch with the Direct2Drive version:
 - The Direct2Drive version of Fallout is not supported.

* Crashes or strange behavior:
 - Let us know how you made it crash, and we'll look into fixing it.

* XBox 360 or PS3 version?
 - Impossible.

* How can I use this with FPS Limiter?
 - Copy the Limiter_D3D9.dll and HookHelper.dll files in to your Fallout folder (same folder as fose_loader.exe and fallout3.exe), then add "-fpslimit 30" (without the quotes) to fose_loader's command line. Change 30 to whatever limit you want.

* Can I modify and release my own version of FOSE based on the included source code?
 - The suggested method for extending FOSE is to write a plugin. If this does not meet your needs, please email the contact addresses listed below.

* How do I write a plugin for FOSE?
 - See PluginAPI.h in the source distribution. Example plugin project coming soon.

* Can I include FOSE as part of a mod pack or otherwise rehost the files?
 - No. Providing a link to http://fose.silverlock.org/ is the suggested method. Exceptions may be given under applicable circumstances; contact us at the email address below.

[ Contact the FOSE Team ]

Before contacting us, make sure that your game launches properly without FOSE first.

Our group email address is: team [at] fose [dot] silverlock [dot] org.  This will forward to the individual members below.

Ian (ianpatt)
Send email to ianpatt+fose [at] gmail [dot] com

Stephen (behippo)
Send email to gamer [at] silverlock [dot] org

Paul (scruggsy)
Send email to scruggsyw [at] comcast [dot] net
