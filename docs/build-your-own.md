# Guide: Build Your Own 

The copilot lamp is fairly easy to assemble with a bit of soldering. The hardest part is patiently waiting for all the parts to print! 😉

In short, it is a few 3D printed parts, a microcontroller, some LEDs and a few wires to connect it all together.

## Buy the Parts

### Materials

- Black PLA Filament [[US]](https://us.store.bambulab.com/products/pla-basic-filament?variant=41078274654344)
- White PLA Filament [[US]](https://us.store.bambulab.com/products/pla-basic-filament?variant=41078274687112)
- 5 WS2812B Addressable LED Matrix (5x5) Panels - [[US]](https://www.amazon.com/dp/B0FLX51BXZ)
- ESP8266 Microcontroller micro-USB + WiFi [[US]](https://www.amazon.com/dp/B081PX9YFV)

- 3 Micro JST Cable Sets [[US]](https://www.amazon.com/dp/B07DL4FNTF)
- Short Micro-USB Extension [[US]](https://www.amazon.com/dp/B0791ZZ3HG)
- (optional) Long micro-USB cable. [[US]](https://www.amazon.com/dp/B0CGDPS336)

### Tools
- Soldering Iron + Solder
- 3D Printer (min 200x200 print area)

> [!NOTE]
> **Tip:** Don't have a 3D printer? Check if your local library has a makerspace.  
> They might be able to print the parts for you! 🤩

# Instructions

The lamp is designed to be assembled by hand, minus the small amount of soldering.

## 1. Print the parts
The .STL files for all of the printable parts are in the `/models` folder.

> [!IMPORTANT]
> Supports are required for several parts.  
> Check the table below to verify.

> [!Tip]  
> The thruster is designed to be easy to change.
> Try making your own decorative base! 🦄 🤩

| Image | Part | Description |
| -- | -- | -- |
<img src="components/helmet-top.jpg" width="200px"> | Helmet Top | ??? |
<img src="components/helmet-bottom.jpg" width="200px"> | Helmet Bottom | Holds the microcontroller, LEDs, and face panel. |
<img src="components/helmet-pin.jpg" width="200px"> | Helmet Pin | Attach the top and bottom helmet parts together. |
<img src="components/face.jpg" width="200px"> | Face | Semitransparent face shield for the LED to glow through. |
<img src="components/goggle-holder.jpg" width="200px"> | Goggle Holder | Contains the LEDs for a single Goggle and mounts to the helmet top. |
<img src="components/goggle-lens.jpg" width="200px"> | Goggle Lens | Diffuses the LEDs. |
<img src="components/goggle-frame.jpg" width="200px"> | Goggle Frame 1 & 2 | Snaps onto the Goggle holder to give it the correct shape. |
<img src="components/thruster.jpg" width="200px"> | Thruster | Space for extra power electronics or a decorative base. |
<img src="components/eyes.jpg" width="200px"> | Eyes 1 and 2 | Swappable eye inserts for the face |

## 1. Install Software

If you order the microcontrollers from the provided link, there is a good chance that 1 of the 5 boards will be bad.
It's important to start with installing the software.

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
