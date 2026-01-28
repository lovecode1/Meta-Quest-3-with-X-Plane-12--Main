# Running Meta Quest 3 + X Plane-12 + MacOS (Plugin + Quest App)

### Introduction:

![alt Pilot with VR + MacBook](https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/blob/main/Images/Pilot.jpg "Title")

I tried all kinds of workarounds to connect the Meta Quest 3 to X-Plane 12 on my MacBook M-series, but nothing worked.

I really wanted the option to enjoy a VR experience on my MacBook. After spending so much on the laptop, I didn’t want to buy a separate Windows gaming PC just to run X-Plane with VR. Plus, when I travel, I can’t take a big PC with me anyway.

So I decided to build my own solution: a custom VR app and an X-Plane plugin. It’s still in development, but I already have a working proof of concept.

The system has two parts: a dedicated Meta Quest 3 app and an X-Plane 12 plugin (See comment below regarding X-Plane 11).

The plugin retrieves the headset’s pose and orientation, applies it to the X-Plane camera, and streams the simulator’s view back to the headset. This creates a usable 3D experience.

For now, you still need a joystick and mouse to control the aircraft, but later I plan to add support for using the Quest controllers directly in X-Plane.

The performance and visual quality will never match a high-end Windows PC with native Quest Link and built-in X-Plane VR support, but the experience is good enough to be enjoyable.

I think there’s real potential here.

# How to Install
### Meta Quest 3 App apk can be download here:
[Google drive link](https://drive.google.com/file/d/1mDzhpilcCMWBR4Mjs2XV3QmcWVuZPK0S/view?usp=drive_link )

It was too big to upload to GitHub.

(If you have an issue downloading the apk with this link please see here [Here](https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/issues/2#issuecomment-3686329576)).

To install the APK on your Meta Quest 3, you can use ADB. (SideQuest is another option).

#### How to setup ADB:
* To install ADB on MacOS run in the terminal: `brew install android-platform-tools`
* Open the Meta app on your phone: Devices → Your headset → Developer Mode → enable
* Restart the headset
* Connect the headset via USB
* In the terminal type: `adb devices`
* Install the APK: `adb install /path/to/apk`

### XP 12 plugin can downloaded here:
[Plugin Directory](https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/tree/main/Mac_VR_Plugin)
Make sure you place the full folder Mac_VR_Plugin in your X Plane plugin folder.
The path is usually `<X Plane installtion path>/Resources/plugins`

### By default for performance we use the Android ADB link to speed up data transfer
By default the XP plugin looks for the Quest on the ip address to 127.0.0.1
Make sure you enable USB access.
To enable USB access see the section below.
In case you want to run on WiFi not on USB then edit the VR ip address [here](https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/blob/main/Mac_VR_Plugin/settings.json).
(You can find the VR ip address in your router settings).

# How to enable USB access:
To enable USB access on a Meta Quest 3, you first need to
enable Developer Mode through the Meta mobile app and then connect your headset to a PC with a USB-C cable. Once connected, a prompt will appear in the headset; select "Allow" to grant USB access, and also choose "Always allow from this computer" for future connections. 
Step 1: Enable Developer Mode 

    Open the Meta mobile app on your phone.
    Go to Settings > Devices > Headset Settings > Developer Mode.
    Toggle the switch to turn on Developer Mode.
    You may need to restart your headset after this step. 

Step 2: Connect the headset to your computer 

    Use a USB-C cable that supports both data and power to connect your headset to your computer.
    Put on your headset. 

Step 3: Allow USB access 

    A prompt will appear in your headset titled "USB Detected" or asking to allow USB debugging.
    Click Allow to grant access to your data.
    Select Always allow from this computer to make future connections easier.

# What type of USB cable is recommended?
Use a high-speed USB cable with the correct power rating. 20Gbs wil be a good choisw. High-quality USB cables include an internal chip that defines their supported speed and power ratings. For the best performance, I recommend using a 20 Gbps USB cable.

# How to run
1. Install the apk on your Meta Quest 3 (It should also work on Quest 3s but I didn't yet test).
2. Make sure the app runs sucessfully on your VR.
3. Place the XP plugin as described above (Was tested on XP 12, it might also work on XP 11).
4. Make sure the plugin runs on your X Plane (You can check the plugin menu and confirm it shows up there).
5. Start X Plane
6. Press on F6 on your mac once you load an airplane.
7. Go back to your VR and make sure the airplane shows up.
8. Press the trigger on the right controller to recenter plane.
9. You can use the thumbsticks on the left/right controller to position you in the cockpit if needed.
10. To get closer to items (e.g. small text in the cokpit) press the grab button on the left controller.
11. Now you can use a joystick to fly the plane.

# X Plane 12 settings:
* In order not to load too much on the MacBook cpu/gpu I'm using this reselution: **`1920 × 1080`** (You can try other resultions and see what works for you best).
* Important: Make sure Vertial FOV is set to **96**, since that's the vertical FOV Meta Quest 3 supports.
* For more settings see here:
![alt Settings Graphics](https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/blob/main/Images/X%20Plane%20Graphics%20Settings.jpg "Title")

* You are welcome to try out other settings.

# Controlling the stream quality:
Here is an important setting that helps you balance quality and performance:

Go to X-Plane menu and select "VR for Mac" -> Settings:

![alt Settings Graphics](https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/blob/main/Images/Stream%20Quality%20Setting.jpg "Image quality menu setting")

Then select the quality:

![alt Settings Graphics](https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/blob/main/Images/Image_Quality_Setting.jpg "Image quality setting")

Then click Apply or Save.

A good range is 90–95.
If you set it too high, performance may drop. If you set it too low, performance will improve but image quality will decrease.
Adjust the slider until you find the balance that looks and feels best for your setup.

# Plance specific vrconfig corrections:
[vrconfig_fixes.md](https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/blob/main/vrconfig_fixes.md)

# X-Plane 11 support:
The plugin does not currently run on X-Plane 11 because it requires an x86-64 binary, and only the ARM version is included at this time.
If there is enough interest in X-Plane 11 support in the future, I will add an x86-64 build.

# Stereoscopic support
At this time, only monoscopic rendering is supported. I could not find a way to get X Plane to product stereoscopic capturing.

# Source code:
Source code is availabe [here](https://github.com/lovecode1/XPlane-12--Meta-Quest-Plugin).

# Desclaimer
* This app is still under development.
* Any feedback is welcome.
* If you find any issue you can post them on issues.
* If I see that there is a lot of interest in this plugin, I will most likely put more work into it.
* This application/plugin is provided “as is” without any warranty of any kind. You install and use it entirely at your own risk.
