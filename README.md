# Running Meta Quest 3 with X Plane-12 - Plugin + App
I tried all kinds of workarounds to connect the Meta Quest 3 to X-Plane 12 on my MacBook M-series, but nothing worked.

I really wanted the option to enjoy a VR experience on my MacBook. After spending so much on the laptop, I didn’t want to buy a separate Windows gaming PC just to run X-Plane with VR. Plus, when I travel, I can’t take a big PC with me anyway.

So I decided to build my own solution: a custom VR app and an X-Plane plugin. It’s still in development, but I already have a working proof of concept.

If anyone is interested in trying it for free, let me know.

The system has two parts: a dedicated Meta Quest 3 app and an X-Plane 12 plugin (it will probably work with XP11 as well, but I haven’t tested that yet).

The plugin retrieves the headset’s pose and orientation, applies it to the X-Plane camera, and streams the simulator’s view back to the headset. This creates a usable 3D experience.

For now, you still need a joystick to control the aircraft, but later I plan to add support for using the Quest controllers directly in X-Plane.

The performance and visual quality will never match a high-end Windows PC with native Quest Link and built-in X-Plane VR support, but the experience is good enough to be enjoyable.

I think there’s real potential here.

# How to Install
Meta Quest 3 App apk can be download here:
https://drive.google.com/file/d/1mDzhpilcCMWBR4Mjs2XV3QmcWVuZPK0S/view?usp=drive_link (It was too big to upload to GitHub).

XP 12 plugin can downloaded here:
https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/tree/main/Mac_VR_Plugin

Make sure to edit https://github.com/lovecode1/Meta-Quest-3-with-X-Plane-12/blob/main/Mac_VR_Plugin/settings.json:
Enter there your local headset ip address.
(You can find the address in your router settings).
