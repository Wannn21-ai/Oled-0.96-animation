# OLED 0.96 Animation

Arduino sketch for a small 0.96-inch OLED display that shows a simple fighting animation between two characters on a 128x64 screen.

This project uses an SSD1306-based I2C OLED module and renders a stylized "pixel fight" scene with:

- two fighters moving toward each other
- punch actions and hit effects
- HP bars
- KO screen and reset cycle

## Features

- 128x64 OLED display support
- two-player simple combat animation
- attack animation with text effect `POW!`
- health bar simulation
- auto-reset after a KO moment
- easy to modify for custom animations or characters

## Hardware Requirements

- Arduino board (Uno, Nano, Mega, etc.)
- 0.96-inch OLED display with SSD1306 controller
- I2C connection
- jumper wires

## Wiring

Connect the OLED to the Arduino using I2C pins:

- VCC -> 3.3V or 5V (depending on your module)
- GND -> GND
- SDA -> A4 on Uno/Nano (or dedicated SDA pin on other boards)
- SCL -> A5 on Uno/Nano (or dedicated SCL pin on other boards)

If you are using a different board, check the board's I2C pins and adjust accordingly.

## Libraries

Install these libraries in Arduino IDE:

- `Adafruit_GFX`
- `Adafruit_SSD1306`

You can install them from the Arduino Library Manager.

## Project Files

- `Test_Oled.ino` — main Arduino sketch
- `LICENSE` — repository license

## How It Works

The sketch is organized into a few main sections:

1. `drawPlayer()`
   - draws a simple stick-figure fighter
   - supports punch and idle poses

2. `drawHit()`
   - displays the `POW!` hit text on the screen

3. `setup()`
   - initializes the OLED and serial communication

4. `loop()`
   - runs the battle sequence in stages:
     - arena entry animation
     - punch exchange loop
     - KO screen
     - reset to starting positions

## Upload Instructions

1. Open `Test_Oled.ino` in the Arduino IDE.
2. Make sure the correct board and COM port are selected.
3. Install the required libraries.
4. Upload the sketch to the board.
5. Power the OLED and watch the animation run.

## Notes

- This project is intentionally simple and lightweight, suitable for learning OLED graphics and animation on Arduino.
- The code is easy to customize for different character designs, colors, or game mechanics.
- The display uses the `SSD1306_SWITCHCAPVCC` initialization mode and the default I2C address `0x3C`.

## License

This project is licensed under the terms of the repository license. See `LICENSE` for details.
