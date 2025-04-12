# PcbDraw

Transform your KiCAD PCB into a beautiful 2D diagram for pinout diagrams or other documentation purposes. No more tedious manual schematic drawings or assembling screenshots!

This tool reads a `.kicad_pcb` file and generates an elegant, SVG-formatted 2D PCB image. Simply insert the generated image into your documentation or README, and you don’t need to have a physical board or open KiCAD to capture a screenshot. Both you and your readers will enjoy a clear, intuitive view of your board layout!

PcbDraw also includes a companion tool—**Populate**—designed to help you easily create and maintain neat assembly manuals in HTML or Markdown format, for instance, by quickly indicating which components to solder where and how to assemble the board.

## Installation

Besides generating 2D diagrams, PcbDraw enables you to programmatically obtain a 3D rendering preview of your PCB (for example, within CI workflows), making it easier to automate the generation of hardware documentation or test reports.

The tool is distributed as a Python package named `pcbdraw` that includes a standalone command-line utility. Note that some library functions require the local installation of [Inkscape](https://inkscape.org/).

### 1. System Dependencies

- [Python 3](https://www.python.org/)
- [Inkscape](https://inkscape.org/)
- It is recommended that you use a virtual environment (virtualenv or conda) to manage dependencies and avoid conflicts.

### 2. Installation Steps

1. **Install PcbDraw**

   ```bash
   pip install pcbdraw
   ```

   If you need additional functionality for handling SVG paths or similar tasks, you may also install other common dependencies:

   ```bash
   pip install svgpathtools
   ```

2. **Verify the Installation**

   ```bash
   pcbdraw --version
   ```
   If a version number or help information is displayed, the installation was successful.

3. **(Optional) Install Populate**

   The Populate tool is typically provided with PcbDraw, but it can also be used on its own. If you need to create HTML/Markdown assembly manuals, consult the Populate documentation and examples for further details.

## Usage

You can find usage examples and scripts in the project's examples directory or the official documentation. The following is a brief demonstration of the basic functionality:

1. **Converting a KiCAD PCB File**

   ```bash
   pcbdraw my_board.kicad_pcb my_board.svg
   ```
   After a brief wait, a 2D PCB diagram named `my_board.svg` will be generated in your current directory.

2. **Generating a 3D Preview** (Optional – additional configuration required)  
   If you require a 3D preview in your CI or automated scripts, please refer to the official documentation for additional setup steps and include the appropriate parameters in your command.

3. **Using the Populate Tool**  
   Populate can generate a concise assembly manual page based on your BOM or other files. For example:
   ```bash
   populate generate my_board.bom.csv --template=html > my_manual.html
   ```
   This command will output a basic assembly manual for your review or sharing.

For further usage details and configuration options, please refer to the [examples](./examples) directory or check the output of `pcbdraw --help` and `populate --help`.

## "PcbDraw Seems Broken"

If you run into any issues during usage or if the functionality does not meet your requirements, please feel free to open an issue on the [Issues](./issues) page. We highly appreciate community feedback and will do our best to help troubleshoot and resolve any problems.

## Contributing

- If you wish to submit new features or bug fixes, feel free to fork the repository and create a pull request.
- For feature requests or suggestions for improvements, please leave a comment in [Issues](./issues).

## Future Work

- We plan to gradually refine and add more modules to support a wider range of PCB layouts and components.
- In the future, we may further optimize automated 3D preview generation and integrate it with additional CI services.

---

If you have any questions or suggestions, please do not hesitate to open an issue in the repository. We look forward to working together to make PcbDraw play an even greater role in hardware documentation and open-source projects!

---
