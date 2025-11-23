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

The model (`.stl`) files for all of the printable parts are in the `/components` folder.

## 1. Print the parts
The .STL files for all of the printable parts are in the `/models` folder.

> [!IMPORTANT]
> Supports are required for several parts.
> Please check your slicer results before printing.

| Image                                                         | Part                    | Description                                                         |
| ------------------------------------------------------------- | ----------------------- | ------------------------------------------------------------------- |
| <img src="../components/helmet-top.jpg" width="200px">        | Helmet Top              | ???                                                                 |
| <img src="../components/helmet-bottom.jpg" width="200px">     | Helmet Bottom           | Holds the microcontroller, LEDs, and face panel.                    |
| <img src="../components/face-panel.jpg" width="200px">        | Face Panel              | Semitransparent face shield for the LED to glow through.            |
| <img src="../components/face-led-guide.jpg" width="200px">    | Face LED Guide          | Maps the light from the LEDs to pixels on the face panel.           |
| <img src="../components/goggle-frames.jpg" width="200px">     | Goggle Frames 1 & 2     | Snaps onto the Goggle holder to give it the correct shape.          |
| <img src="../components/goggle-lens.jpg" width="200px">       | Goggle Lens 1 & 2       | Diffuses the LEDs.                                                  |
| <img src="../components/goggle-led-guides.jpg" width="200px"> | Goggle LED Guides 1 & 2 | Maps the light from the LEDs to pixels on the face panel.           |
| <img src="../components/goggle-holders.jpg" width="200px">    | Goggle Holders          | Contains the LEDs for a single Goggle and mounts to the helmet top. |
| <img src="../components/thruster-usb.jpg" width="200px">      | Thruster (USB)          | Space for securing the USB cable or creating an alternative base.   |


1. Connect the microcontroller to your computer using a USB cable.
1. Open a web browser and navigate to the [WLED install page](https://install.wled.me/).
1. In the drop down, ensure version `0.15.x` is selected.
1. Click the **Install** button and a window will appear.
Select the USB serial device.
1. Follow the instructions and wait a few minutes for the install.
    - If this seems to have trouble, try a different board.
1. When asked, enter your WiFi details.
    - Accessing the device locally is required to upload the configuration.
1. When the install is finished, click the **Visit Device** button.
1. On the device's main page, in the top right, click the **Config** button.
1. At the bottom, select **Security and Updates**
1. Scroll to the bottom and look for the backup options.

   (pending: premade config and playlists)
## 2. Pre-Assembly and Testing

### LED Matrix - Face

Let's connect 3 LED matrix boards to be the lights for Copilot's face.

1. Align 3 of the matrix boards with the text facing the same direction. Tape them together.

> [!WARNING]  
> The Orientation must be correct.
> `DIN` will align with `DOUT` on the board next to it.


2. Link the boards by soldering them together. Only 1 `GND` is necessary per connection.


3. Attach a plug-style JST cable to the `DIN` (right side from back view).


4. Attach a **plug-style** JST cable to the `DIN` (right side from back view).

  - Red Wire: `VCC` (power)
  - White Wire: `GND` (ground)
  - Yellow Wire: `DIN` (digital)


5. Attach a **socket-style** JST cable to the `DOUT` (left side from back view).

  - Red Wire: `VCC` (power)
  - White Wire: `GND` (ground)
  - Yellow Wire: `DOUT` (digital)

### LED Matrix - Goggles

Let's prepare 2 LED matrix boards for Copilot's goggles.

1. Attach a **plug-style** JST cable to the `DIN` (right side from back view).


1. On 1 of the 2 boards, attach a **socket-style** JST cable to the `DIN` (right side from back view).


1. Attach a **socket-style** JST cable to the microcontroller.
  
  - Red Wire: `5V` (power)
  - White Wire: `G` (ground)
  - Green Wire: `D4` (digital)


2. Attach the short micro-usb extension.
    

### Pre-check Testing

1. Connect the 3x LED panel and the 2 goggle LED panels.
1. Connect the LEDs to the microcontroller.
1. Plug in the USB cable to apply power.
1. The LEDs should randomly glow rainbow colors.


## 3. Main Assembly

### Face Install

1. Collect the 3x LED panel, Helmet Bottom, and Face parts.

2. Slide the 3x LED panel into the second groove.


3. Slide the Face into the first groove.

### Goggles Install

1. Collect Goggle Frames 1 & 2, both Goggle Holders, both Lens, and the 2 single LED Matrix panels.

2. Slide the cables for an LED panel through the hole of a Goggle Holder.

3. Align the pins and push down to attach the LED panel. It will hold by friction.

   > 🪧 **Note**: Orientation does not matter yet.

4. Select a Goggle Frame and insert a lens. It will hold by friction.

5. Slide the combined Goggle Frame + Lens over a Goggle Holder.

   - Goggle Frame 1: Double cabled LED panel
   - Goggle Frame 2: Single cabled LED panel

   > ❗️ **IMPORTANT:** Double-check the frame orientation!
   > Compare the shape and text on the LED matrix to align.

5. Insert Goggle 1 into Helmet Top (left side if looking at Copilot).

5. Insert Goggle 2 into Helmet Top (lefrightt side if looking at Copilot).

### Microcontroller Install

1. Insert the microcontroller into the Helmet Bottom.

1. Twist the USB cable around some of the left cable guides and pinch it into the holder.

1. Connect the LED Matrix cable cables to the microcontroller.
![](assemble/electronics-plate-4.jpg)

## 4. Final Assembly

1. Apply power and verify all lights turn on.

2. Wait a moment and verify WiFi activates.

3. Insert the pins into Helmet Bottom.

4. Slide Helmet Top onto Helmet Bottom.

1. You are finished! See the main [README](../README.md) for usage info. Plug it in and enjoy!

## Other Advanced Tasks

### Switch to USB-C.

- ESP8266 Microcontroller USB-C + WiFi [[US]](https://www.amazon.com/dp/B0BHW1CNCM)
- Short USB-C Extension [[US]](https://www.amazon.com/dp/B01D8FMPP6)

## Troubleshooting

### Reset Device 

- Reset WiFi: hold button 0 for >6 seconds.
- Reset WLED: hold button 0 for >12 seconds.

# Reference

## Manually Configure

These are the settings for manually configuring a device the same
as the premade configuration file.

### LED Preferences

- Maximum current: 850mA
- WS281x
- GPIO 2
- Turn LEDs on after power up/reset: checked

### WiFi Setup

DNS address: copilot-lamp-3d.local
AP SSID: copilot-lamp-3d
AP Pass: copilot-lamp-3d
Disable WiFi Sleep: checked

