# Guide: Build Your Own

The copilot lamp is fairly easy to assemble with a bit of soldering. The hardest part is patiently waiting for all the parts to print! 😉

In short, it is a few 3D printed parts, a microcontroller, some LEDs and a few wires to connect it all together.

![](build-your-own/components-overview.jpg)

## 1. Buy the materials

### Materials

- Black PLA Filament [[US]](https://us.store.bambulab.com/products/pla-basic-filament?variant=41078274654344)
- White PLA Filament [[US]](https://us.store.bambulab.com/products/pla-basic-filament?variant=41078274687112)
- (5 Qty) WS2812B Addressable LED Matrix (5x5) Panels [[US]](https://www.amazon.com/dp/B0FLX51BXZ)
- ESP8266 Microcontroller micro-USB + WiFi [[US]](https://www.amazon.com/dp/B081PX9YFV)
- (3 Qty) Micro JST Cable Sets [[US]](https://www.amazon.com/dp/B07DL4FNTF)
- Long micro-USB cable. [[US]](https://www.amazon.com/dp/B0CGDPS336)

> [!TIP]
> You can also use USB-C. I personally do micro-USB because the board and power cables are cheaper.

### Tools

- Soldering Iron + Solder
- 3D Printer (min 200x200 print area)
- Pliers

> [!TIP]
> Don't have a 3D printer? Check if your local library has a makerspace.  
> They might be able to print the parts for you! 🤩

## 2. Print the parts

The model (`.stl`) files for all of the printable parts are in the `/models` folder.

## 1. Print the parts
The .STL files for all of the printable parts are in the `/models` folder.

> [!IMPORTANT]
> Supports are required for several parts.
> Please check your slicer results before printing.

| Image                                                     | Part                    | Description                                                         |
| --------------------------------------------------------- | ----------------------- | ------------------------------------------------------------------- |
| <img src="../models/helmet-top.jpg" width="200px">        | Helmet Top              | ???                                                                 |
| <img src="../models/helmet-bottom.jpg" width="200px">     | Helmet Bottom           | Holds the microcontroller, LEDs, and face panel.                    |
| <img src="../models/face-panel.jpg" width="200px">        | Face Panel              | Semitransparent face shield for the LED to glow through.            |
| <img src="../models/face-led-guide.jpg" width="200px">    | Face LED Guide          | Maps the light from the LEDs to pixels on the face panel.           |
| <img src="../models/goggle-frames.jpg" width="200px">     | Goggle Frames 1 & 2     | Snaps onto the Goggle holder to give it the correct shape.          |
| <img src="../models/goggle-lens.jpg" width="200px">       | Goggle Lens 1 & 2       | Diffuses the LEDs.                                                  |
| <img src="../models/goggle-led-guides.jpg" width="200px"> | Goggle LED Guides 1 & 2 | Maps the light from the LEDs to pixels on the face panel.           |
| <img src="../models/goggle-holders.jpg" width="200px">    | Goggle Holders          | Contains the LEDs for a single Goggle and mounts to the helmet top. |
| <img src="../models/thruster-usb.jpg" width="200px">      | Thruster (USB)          | Space for securing the USB cable or creating an alternative base.   |

## 3. Prepare the Microcontroller

Let's install the software that will control our LEDs,
and configure the regions for easily changing the face, eyes, and googles.

### 3.1 Install WLED

1. Connect the microcontroller to your computer using a USB cable.
1. Open a web browser and navigate to the [WLED install page](https://install.wled.me/).
1. In the drop down, ensure version `0.15.x` is selected.
1. Click the **Install** button and a window will appear.
1. Select the USB serial device.
   - If no device is appearing, follow WLEDs tips about installing drivers.
   - Tip: Newer Macs seem to not include the driver by default anymore.
1. Follow the instructions and wait a few minutes to install.
   - If this seems to have trouble, try a another board.
1. When asked, enter your WiFi details.
   - Accessing the device locally is required to upload the configuration.
1. When the install is finished, click the **Visit Device** button.

### 3.2 Configure WLED

Let's upload a configuration for the device's LED orientation, and then presets to assign regions with names like "Face", "Eye", and "Goggle".

1. On the device's main page, in the top right, click the **Config** button.

2. Scroll to the bottom and select **Security and Updates**.

3. Find the **Backup & Restore** section.

4. For the **Restore Presets** option. Upload the following file.

   File: [`/wled/presets_playlists.json`](../wled/presets_playlists.json)

   This will install the following:

   - Segments defininig the face, eyes, and goggles.
   - Presets with example face animations.
   - Presets with example goggle animations.
   - Presets with example eye colors and locations.
   - A playlist to apply a combination of presets on boot.

5. For the **Restore Configuration** option, upload the following file.

   File: [`/wled/configuration.json`](../wled/configuration.json)

   This will install following:

   - Set the device to use 124 LEDs and max 1 amp power.
   - Assign a 2D layout for the 5 LED matrix panels.
   - Configure a timer option to turn on the lamp at 9am and off at 5pm. - Enable the option to broadcast a WiFi network named `copilot-lamp-3d`, if no WiFi is found.
   - Configure a timer option to turn on the lamp at 9am and off at 5pm.
   - Set the device's network name to `copilot-lamp-3d`.

### 3.3 Attach the LED cable

1. Attach a **socket-style** JST cable to the microcontroller.

   - Red Wire: `5V` (power)
   - Black Wire: `G` (ground)
   - Yellow Wire: `D4` (digital)

   <img src="build-your-own/3-1.jpg"/>
   <img src="build-your-own/3-2.jpg"/>

## 4. Prepare the Face LEDs

Let's connect 3 LED matrix boards together. This will be the lights for Copilot's face.

1. Align 3 of the matrix boards with the text facing the same direction. Tape them together.

   > ⚠️ **Warning:** The Orientation must be correct.
   > `DIN` will align with `DOUT` on the board next to it.

   <img src="build-your-own/4-1.jpg"/>

2. Link the boards by soldering them together. Only 1 `GND` is necessary per connection.

   <img src="build-your-own/4-2.jpg"/>

   > 🪧 **Note:** Soldering can be difficult, especially across a gap. Just be patient and keep trying. 🧐

3. Attach the JST cables.

   - Make sure the cables run toward the middle, not outwards.
   - Make sure the cables do not extend past the edge of the panel. Otherwise, it will not slide into the mounting slot.
   - Pay attention to the cable location and type.

     - `DIN` (right side) uses a plug-style cable.
     - `DOUT` (left side) uses a socket-style cable.

   - Pin mapping
     - Red Wire: `VCC` (power)
     - Black Wire: `GND` (ground)
     - Yellow Wire: `DIN` or `DOUT` (digital)

   <img src="build-your-own/4-4.jpg"/>

## 5. Prepare the Goggles LEDs

Let's prepare 2 LED matrix boards for Copilot's goggles.

- One has both a plug-style cable and socket-style cable.
- One has only a plug-style cable.

   <img width="48%" src="build-your-own/5-1.jpg"/>
   <img width="48%" src="build-your-own/5-3.jpg"/>

1. With one LED matrix, attach both a **socket-style** and **plug-style** cable.

   - Make sure the cables run toward the middle, not outwards.
   - Pay attention to the cable location and type.

     - `DIN` (right side) uses a plug-style cable.
     - `DOUT` (left side) uses a socket-style cable.

   - Pin mapping
     - Red Wire: `VCC` (power)
     - Black Wire: `GND` (ground)
     - Yellow Wire: `DIN` or `DOUT` (digital)

   <img src="build-your-own/5-2.jpg"/>

1. With another LED matrix, attach a **plug-style** cable.

   - Make sure the cables run toward the middle, not outwards.
   - Pin mapping
     - Red Wire: `VCC` (power)
     - Black Wire: `GND` (ground)
     - Yellow Wire: `DIN` (digital)

   <img src="build-your-own/5-4.jpg"/>

## 6. Electronics Check

1. Connect the microcontroller, Face LED panel, and 2 Goggle LED panels together.

1. Apply power to the microcontroller by plugging in via USB.

1. Verify the lights appear. Colors do not matter.

   Examples:

   WLED's default if no default provided.
   <img src="build-your-own/6-1.jpg"/>

   Default set to a preset with random color animation.
   <img src="build-your-own/6-2.jpg"/>

## 7. Face Install

1. Collect the following parts:

   - Helmet Bottom
   - Face LED Guide
   - Face LED LED panel
   - Microcontroller

2. Slide the Face LED panel into the groove 1 (furthest inward).

   <img src="build-your-own/7-1.jpg"/>

3. Slide the LED Guide into the groove 2 (middle option).

   <img src="build-your-own/7-2.jpg"/>

4. Coming from the front, slightly bend the Face panel and wrap it around the LED Guide. to insert it.

   - The side mount flaps will extend into groove 3 (furthest outward).
   - The bottom mount fap will slide downward into a groove in the chin area.

   <img src="build-your-own/7-3.jpg"/>

## 8. Goggles Preparation

1. Collect the following parts:

   - Goggle Frames 1 & 2
   - Goggle Holders 1 & 2
   - Google Lens 1 & 2
   - Goggle LED Guides 1 & 2
   - Both single LED Matrix panels.

   <img src="build-your-own/8-1.jpg"/>

2. Slide the **double-cabled** LED panel's cables through the hole of a Goggle Holder. Align the pins and push down to attach the LED panel.

   - It will hold by friction.
   - Orientation in the holder does not matter.

   <img src="build-your-own/8-2.jpg"/>

3. Rotate the combined unit so the text is upright, same as picture above.

4. Insert the LED Guide.

   - It will hold by friction.
   - Orientation in the holder does not matter.

   <img src="build-your-own/8-3.jpg"/>

5. Select Goggle Frame 1 and insert a lens.

   - It will hold by friction.
   - Place the textured side facing outward.

   <img src="build-your-own/8-4.jpg"/>

6. Slide the Goggle Frame over the Goggle Holder .

   - ❗️ **IMPORTANT:** Verify the text is upright.
   - ❗️ **IMPORTANT:** The straighter edge will be on the **right**.

   <img src="build-your-own/8-5.jpg"/>

   <img src="build-your-own/8-6.jpg"/>

7. Repeat the above steps with the **single-cable** LED Panel.

   - ❗️ **IMPORTANT:** Verify the text is upright.
   - ❗️ **IMPORTANT:** The straighter edge will be on the **left**.

   <img src="build-your-own/8-7.jpg"/>

   <img src="build-your-own/8-8.jpg"/>

## 9. Goggles Install

1. Collect the following parts:

   - Top Helmet
   - Goggle 1
   - Goggle 2

   <img src="build-your-own/9-1.jpg"/>

1. Insert Goggles 1 and 2 into the respective ports.

   - The flatter edge will be in the middle.

   <img src="build-your-own/9-2.jpg"/>

1. Flip the combined unit over and connect the 2 cables togther.

   <img src="build-your-own/9-3.jpg"/>

## 10. Microcontroller Install

Let's mount the microcontroller in the helmet and connect it to the LEDs and USB cable.

1. Slide the microcontroller into the slot in the Helmet Bottom.

   <img src="build-your-own/10-1.jpg"/>

1. Connect the Face LED cable and Microcontroller cable.

   <img src="build-your-own/10-2.jpg"/>

1. Pass the USB cable through the lower hole and plug it into the Microcontroller.

   <img src="build-your-own/10-3.jpg"/>

## 11. Attach Helmets and Thruster

Let's combine the 2 halves and then route the USB cable through the thruster.

1. Orient the two assemblies similar to the below picture then connect the Goggle LEDs and Face LEDs.

   <img src="build-your-own/11-1.jpg"/>

2. Flip the Helmet Top assembly over onto Helmet Bottom, align the pins, and gently press downward to connect them.

   - **Tip:** Do not push it all the way down yet!

   <img src="build-your-own/11-2.jpg"/>

3. Tilt the lamp on its side.

4. In the Thruster, route the usb cable through several of the cable guides and out through the slot.

   <img src="build-your-own/11-3.jpg"/>

5. Align the round thruster with the ring/groove on the bottom of the lamp. Press it inwards for it to snap into place.

   - The bottom of the lamp and the thruster have 3 matching notches.
   - The cable will orient out of the back of Copilot.

   <img src="build-your-own/11-4.jpg"/>

## 4. Final Checks

1. Apply power and verify all lights turn on.

2. Wait a moment and verify WiFi activates.

3. Try accessing the lamp from your phone or computer.

4. Try various color animations.

5. You are finished! See the main [README](../README.md) for usage info. Plug it in and enjoy!
