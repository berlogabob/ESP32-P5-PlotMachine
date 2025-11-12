# ESP32-P5-PlotMachine
A DIY ESP32 adaptation of the Neje laser engraver for pen plotting and generative art.
# ESP32-Neje-Plotter

![Project Banner](https://via.placeholder.com/800x200/000000/FFFFFF?text=ESP32+Neje+Plotter) <!-- Replace with actual image if available -->

## Overview

This project transforms a affordable Neje laser engraver into a versatile plotting machine using an ESP32 microcontroller. By replacing the laser head with a pen, pencil, or other drawing tool, you can create precise drawings, generative art, and even ML-driven designs. The setup includes:

- **Hardware Control**: ESP32 interfaces with the Neje's stepper motors and GRBL firmware for accurate movement.
- **Web Interface**: Built with [p5.js](https://p5js.org/) for interactive sketching and [ml5.js](https://ml5js.org/) for machine learning features like pose detection to guide the plotter.
- **Customization**: Easily swap tools for different effects (e.g., ink, charcoal, or 3D printing nozzles).

Perfect for makers, artists, and hobbyists exploring CNC plotting on a budget!

## Features

- ESP32-based control for wireless operation.
- GRBL-compatible commands for G-code execution.
- p5.js canvas for real-time design preview and export.
- ml5.js integration for AI-assisted patterns (e.g., neural style transfer or gesture-based drawing).
- Modular tool head for pens, lasers, or extruders.
- Open-source hardware schematics and code.

## Hardware Requirements

- Neje laser engraver (e.g., DK-8-KZ model).
- ESP32 development board (e.g., ESP32-WROOM-32).
- Stepper motor drivers (A4988 or similar, if modifying).
- Tool head adapter (3D-printable STL files provided in `/hardware/`).
- Power supply (12V, matching Neje specs).
- USB cable for initial flashing; WiFi for runtime control.

## Software Setup

### 1. ESP32 Firmware
- Install [Arduino IDE](https://www.arduino.cc/en/software) with ESP32 board support.
- Flash GRBL-ESP32 (forked for Neje compatibility) via `/firmware/` sketches.
- Connect ESP32 to Neje's control board (pins: TX/RX for serial, GPIO for step/dir/enable).

### 2. Web Interface
- Clone this repo and open `/interface/index.html` in a browser.
- Uses p5.js for drawing canvas and ml5.js for ML models.
- Send G-code to ESP32 over WebSerial API (Chrome/Edge recommended).

### 3. Dependencies
- **ESP32**: GRBL-ESP32 library.
- **Frontend**: p5.js (CDN), ml5.js (CDN), no build tools needed initially.

## Getting Started

1. **Assemble Hardware**:
   - Follow `/hardware/schematics.pdf` for wiring.
   - 3D-print the tool adapter from `/hardware/tool_head.stl`.

2. **Flash ESP32**:

3. **Test Plotting**:
- Connect via serial monitor: Send `G28` (home) then `G1 X10 Y10` (move).
- Open web interface, draw a shape, and hit "Plot!"

4. **Advanced: ML Integration**:
- Load a ml5 model (e.g., BodyPix for pose-to-path conversion).
- Example sketch in `/interface/ml_sketch.js`.

## Usage Examples

- **Simple Plot**: Draw in p5.js editor, export G-code, upload to ESP32.
- **Generative Art**: Use Perlin noise in p5.js to create organic patterns.
- **ML-Driven**: Webcam detects hand gestures; ml5.js converts to plot paths.

![Example Plot](https://via.placeholder.com/400x300/CCCCCC/000000?text=Sample+Pen+Plot) <!-- Add real example image -->

## Contributing

1. Fork the repo.
2. Create a feature branch (`git checkout -b feature/amazing-tool`).
3. Commit changes (`git commit -m 'Add pen adapter support'`).
4. Push and open a PR.

Issues and ideas welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## License

This project is open-source under the MIT License. See [LICENSE](LICENSE) for details.

## Acknowledgments

- Inspired by [Neje engravers](https://neje.shop/) and [GRBL project](https://github.com/gnea/grbl).
- Thanks to the p5.js and ml5.js communities for creative tools.

---

⭐ Star this repo if you plot something cool! Questions? Open an issue.