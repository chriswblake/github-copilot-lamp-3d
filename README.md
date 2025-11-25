# GitHub Copilot Lamp 3D

<img height="250" align="right" alt="Various lamp parts on a table" src="docs/README/welcome-anim.webp" />

A fun and playful lamp to match the energy of GitHub Copilot. It's 3D printable and fairly easy to assemble!

- WiFi Connected
- Powered by [WLED](https://kno.wled.ge/)
- Compatibile with [Home Assistant](https://www.home-assistant.io/)

#### Other Fun GitHub Lamps

- [Copilot Lamp (2D)](https://github.com/chriswblake/github-copilot-lamp)
- [Octolamp](https://github.com/martinwoodward/octolamp)

## Build your own 🤓

That's cool and all, but how do I make one?!  
Check out the [build your own](docs/build-your-own.md) page for a step-by-step guide. 🧑‍🚀

## How to Use

If you received your lamp prebuilt, is has already been configured and is ready to use. Simply plug it in with a USB cable and power brick with at least 1 amp. The lamp will turn on with an "rainbow" like green effect.

### Connect with the App

1. Ensure you are on the same WiFi network.

2. Download the WLED app.
   - [iOS App](https://apps.apple.com/us/app/wled/id1475695033)
   - [Android App](https://play.google.com/store/apps/details?id=com.aircoookie.WLED)
   - The lamp can also be accessed with web browser by navigating to http://copilot-lamp-3d.local.
3. Open the app and the lamp should automatically be discovered.

### Predefined Segments, Presets, and Playlists

There are 5 predefined segments for the face, eyes, and goggles. There are also various example presets that use them to easily adjust the look of Copilot.

Below are some examples of changing the eye color, eye position, and applying animations to the face.

<div>
<img src="docs/README/segments.png" width="24%">
<img src="docs/README/presets-eyes-goggles-color.png" width="24%">
<img src="docs/README/presets-eyes-position.png" width="24%">
<img src="docs/README/presets-face.png" width="24%">
</div>

> [!TIP]
> You can also do scrolling text! Check out the "Hello World" example.

### Connect to WiFi

Want full control over your lamp? Connect it to your WiFi network! (2.4ghz only)
If not connected to an existing wifi, it will broadcast a tempory wifi network for setup.

1. On your phone or computer, search for the wifi network `copilot-lamp-3d` and connect to it.
   - Default password is `copilot-lamp-3d` or `wled1234`.
1. Wait a moment and a temporary login-style web browser will appear. If no browser appears, open a web browser navigate to http://copilot-lamp-3d.local.
1. In the top right, click the **Config** gear icon to open the settings menu.
1. Select **WiFi Setup**.
1. Enter you home's wifi name and password. Click **Save & Connect**. Wait a moment for the lamp to restart.
1. Reconnect your phone or computer to your home wifi.

<div>
<img src="docs/README/connect-wifi-1.png" width="24%">
<img src="docs/README/connect-wifi-2.png" width="24%">
<img src="docs/README/connect-wifi-3.png" width="24%">
<img src="docs/README/connect-wifi-4.png" width="24%">
</div>

### Example Animations

<table>
<tr>
<td>
    <img width="100%" alt="anim-1" src="https://github.com/user-attachments/assets/a59d2198-77e3-4eaf-8cdb-22fcb5223507"/>
</td>
<td>
    <img width="100%" alt="anim-2" src="https://github.com/user-attachments/assets/d70c0699-456e-4821-93e8-3b4a0b9df80d"/>
</td>
<td>
    <img width="100%" alt="anim-3" src="https://github.com/user-attachments/assets/f1a80026-b179-4c4e-9357-114f61a2301c"/>
</td>
<td>
    <img width="100%" alt="anim-4" src="https://github.com/user-attachments/assets/eb863c1a-6094-4a84-a136-324d11affdec"/>
</td>
</tr>
</table>
