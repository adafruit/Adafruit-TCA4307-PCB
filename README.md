## Adafruit TCA4307 Hot-Swap I2C Buffer with Stuck Bus Recovery PCB

<a href="http://www.adafruit.com/products/5159"><img src="assets/5159.jpg?raw=true" width="500px"><br/>
Click here to purchase one from the Adafruit shop</a>

PCB files for the Adafruit TCA4307 Hot-Swap I2C Buffer with Stuck Bus Recovery. 

Format is EagleCAD schematic and board layout
* https://www.adafruit.com/product/5159

### Description

As we've been adding  STEMMA QT connectors to our breakouts and dev boards, folks have been really enjoying the simplicity and speed of plugging in I2C sensors and devices for quick iteration and design. That's all good, but I2C wasn't really designed for hot-plugging. You're kinda supposed to have everything connected once on boot and never mess with it - I2C was specified for on-board connections. And, folks who have experimented with hot-plugging I2C devices eventually have discovered that if you plug in or unplug at the wrong moment you can cause the bus to hang due to an extra SCL pulse or an unexpected capacitive load.

The Adafruit TCA4307 Hot-Swap I2C Buffer breakout here solves that problem. It's specifically designed to take a non-hot-swap protocol (I2C) and protect the controller from wayward peripherals messing with the bus during attach/detach.

Usage is super simple. Connect the left side (IN) to your main board controller - Arduino, Raspberry Pi, Feather, etc. Then connect any I2C sensors you like to OUT side. Power is connected through - this isn't a power isolator, just a bus buffer. You can use 2.3 to 5.5V DC power and logic levels.

The chip can handle up to 400KHz I2C clock rates and even has stuck bus recovery: it automatically disconnects the bus if it detects either SDAOUT or SCLOUT are low for about 40 ms. Once the bus is disconnected, the device automatically generates up to 16 pulses on SCLOUT to attempt to reset the device which is holding the bus low.

There's also an extra ENable pin, if you want to disconnect the in and out sides, and a READY pin that will let you know if the peripheral is buffer-connected to the controller (and is safe to attempt communication with)

To get you going fast, we spun up a custom-made PCB in the STEMMA QT form factor, making it easy to interface with. The STEMMA QT connectors on either side are compatible with the SparkFun Qwiic I2C connectors. This allows you to make solderless connections between your development board and the TCA4307 or to chain it with a wide range of other sensors and accessories using a compatible cable. QT Cable is not included, but we have a variety in the shop.

### License

Adafruit invests time and resources providing this open source design, please support Adafruit and open-source hardware by purchasing products from [Adafruit](https://www.adafruit.com)!

Designed by Limor Fried/Ladyada for Adafruit Industries.

Creative Commons Attribution/Share-Alike, all text above must be included in any redistribution. 
See license.txt for additional details.
