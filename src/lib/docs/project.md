# Project Guidelines
Create a git repository for your dongle! In your repository create a `JOURNAL.md` file.

1. At the top include:
	- `[Your Project Name]`
	- `[A Brief Project Description]`
	- `[Total Hours]` - approximately how long you spent on your project

2. **Each session you work on your project, write a journal entry!** 
	- *It can be what you built, learned, messed up, decided, or something else completely.*
	- List how much time you spent
	- Give it a title and add images!
	- **Here is an example of a great journal:**

> **June 8: Got the screen to work!!**
> *Time Spent: 3 hours*
> I got the raspberry pi to actualy display on the LCD! Can't believe it actually works
> I based the wiring off of the pi-tin project originally, but they used an ili9341 display instead of the st7735r I was reusing from sprig. That meant that I had to figure out not only how they got it to display originally, but also how to modify that to use the ST7735R drivers instead
> <img src="https://cdn.hackclub.com/01a03ccd-36d9-7a67-8539-f2a082dcaae3/good-journal-image-1.webp" alt="" width="600px">
> Fortunately for us, the pi-tin project actually documented how the software was set up! They actually cross-reference an adafruit script, which is a derivative of one from pimoroni.
> In short, here's how the original method worked:
> Install FBCP (framebuffer copy) drivers, which captures whatever would've been outputted to HDMI and allows you to redirect it somewhere else
> Modify the dtoverlays (device tree overlay) in /boot/config.txt to use the built-in kernel drivers for the ILI9341
> Reboot. The framebuffer should automatically redirect everything to the display.
	
There is no required journal length; however, the more the merrier! It serves as something you can reference as you continue your project (understanding why you made the choices you did), and is rewarding to read later on.