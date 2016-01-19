# Device Emulation

Note: This README specifically covers Chrome functionality, but many of the things covered are equally applicable to other major browsers.


### What
Device emulation is the process of forcing the browser to imitate a particular device by limiting its screen-size, changing the screen resolution, as well as emulating touch events and limiting network speed to spoof 2G and 3G devices.

It is a feature commonly included in developer tools in major browsers.

### Why
Device emulation is a cheap and easy way of testing the design and functionality of your website on a variety of devices. Without some kind of emulation, developers would need access to a huge variety of hardware to test on.

### How
Open dev tools, and click the *Toggle device mode* button in the top left hand corner.

![oops](https://developer.chrome.com/devtools/docs/device-mode-files/device-mode-initial-view.png)

The webpage will immediately shrink to the default viewport size. All of the regular dev tools features can be used in this mode.

##### Viewport Size
The viewport size can be set to some presets (typically emulating popular smartphones and tablets) or to a custom size.

![oops](https://developer.chrome.com/devtools/docs/device-mode-files/device-and-network-tools.png)

![oops](https://developer.chrome.com/devtools/docs/device-mode-files/screen-controls.png)


##### Media Queries
You can inspect media queries by opening the media query visualiser in the top left hand corner:

![oops](https://developer.chrome.com/devtools/docs/device-mode-files/media-query-inspector-ruler.png)

Queries are colour coded by target: blue queries target maximum width, green queries target width in a range, and orange queries target a minimum width.


##### Sensor Emulation
Smartphones and tablets have a variety of sensors which development machines typically don't, and so the behaviour of the website in response to these sensor outputs can be difficult to test.

The dev tools have a built-in sensor emulator that can be accessed by clicking the ellipsis in the top right hand corner of the *Device mode* view.

![oops](https://developer.chrome.com/devtools/docs/device-mode-files/emulation-drawer-sensors.png)

You can then emulate touch, GPS and accelerometer data, for example for a geolocation web-app or a step counter web-app.


### Links
See the full documentation for [Chrome Device Mode](https://developer.chrome.com/devtools/docs/device-mode), upon which this README is based. For Firefox browsers, see [this link](https://developer.mozilla.org/en/docs/Tools/Responsive_Design_View)
