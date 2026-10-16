# GerberView3D

**A browser-based Gerber PCB viewer with interactive 2D and 3D
visualization.**

GerberView3D lets you load a PCB's Gerber and drill files, inspect its
layers in 2D, and generate an interactive 3D board preview. It runs
locally in your web browser: your design files are not uploaded to a
server, and no account is required.

## Features

-   **2D PCB view** --- inspect the loaded board and its artwork.
-   **Interactive 3D view** --- explore the board from different angles,
    including isometric, top, and bottom views.
-   **Gerber ZIP support** --- load a ZIP archive containing a board's
    Gerber and drill files.
-   **Individual file loading** --- load loose Gerber and drill files
    without first creating an archive.
-   **Drag and drop** --- drop a Gerber ZIP or supported files into the
    viewer.
-   **Automatic layer recognition** --- identify common Gerber
    extensions and assign recognized layers.
-   **Layer visibility controls** --- show or hide individual layers;
    the 3D view follows the layer selections.
-   **Drill-hole support** --- display drill holes and plated/non-plated
    opening geometry where represented by the supplied drill data.
-   **Board outline support** --- use the board outline to construct the
    3D board. A closed outline is required for 3D rendering.
-   **3D lighting controls** --- adjust lighting to improve visibility
    and appearance.
-   **View controls** --- reset the 3D view and switch between
    predefined camera orientations.
-   **Fullscreen mode** --- expand the viewer to fullscreen; press `Esc`
    to exit.
-   **PNG screenshots** --- save the current 2D or 3D view as an image.
    The 3D screenshot is exported at twice the viewer canvas resolution.
-   **Runs locally** --- files stay in the browser; no upload, login, or
    server-side processing is needed.

## Supported inputs

GerberView3D is intended for Gerber PCB manufacturing outputs and
associated drill files. Common layer extensions recognized by the viewer
include:

  -----------------------------------------------------------------------
  Extension                           Common use
  ----------------------------------- -----------------------------------
  `.GTL`                              Top copper

  `.GBL`                              Bottom copper

  `.GTS`                              Top solder mask

  `.GBS`                              Bottom solder mask

  `.GTO`                              Top silkscreen

  `.GBO`                              Bottom silkscreen

  `.GML`                              Mechanical / board outline
                                      (depending on the CAD export
                                      configuration)

  `.TXT`                              Commonly used for Excellon drill
                                      data
  -----------------------------------------------------------------------

Layer names and extensions vary between CAD tools and export settings.
The viewer also accepts ZIP archives and loose Gerber/drill files, but
exact recognition depends on the filenames and contents supplied.

## How to use

1.  Open `gerberview3d.htm` in a modern browser.
2.  Drop a Gerber ZIP into the upload area, or choose the relevant files
    manually. You can also use drag and drop.
3.  Wait for the files to be parsed and the layers to be identified.
4.  Use the layer controls to show or hide the required layers.
5.  Switch between **2D** and **3D**.
6.  In 3D, rotate with the left mouse button, zoom with the mouse wheel,
    and pan with the right mouse button.
7.  Adjust the lighting sliders as needed.
8.  Select **Full screen** to enlarge the view. Press `Esc` to leave
    fullscreen.
9.  Select **Save screenshot** to export the current view as a PNG.

For the 3D view, make sure the board outline is present and closed.

## Technical notes

GerberView3D is a client-side HTML application. Its bundled libraries
include:

-   [Three.js](https://threejs.org/) --- 3D rendering.
-   [tracespace](https://github.com/tracespace/tracespace) --- Gerber
    parsing and plotting.
-   [fflate](https://github.com/101arrowz/fflate) --- ZIP archive
    reading.

The application is designed to run locally in a browser and does not
require a backend service.

## Known limitations

-   Gerber clear polarity (`LPC`) is not applied.
-   Component 3D models are not included.
-   Inner copper layers are not drawn.
-   The 3D view requires a closed board outline.
-   Rendering and supported Gerber features depend on the input files
    and the browser's graphics capabilities.

## Privacy

All file processing takes place in your browser. The viewer does not
upload your PCB files to a remote server and does not require an
account.

## License

GerberView3D is released under the **MIT License**. See
[`LICENSE`](LICENSE) for the full license text.

Third-party libraries are distributed under their respective licenses;
see their project documentation for details.

## Contributing

Bug reports, feature requests, and pull requests are welcome. When
reporting a problem, include the browser name/version, the steps needed
to reproduce it, and a small sample of the relevant Gerber/drill files
if possible.

## Disclaimer

GerberView3D is a visualization tool. Always verify manufacturing data
with your PCB CAD software and appropriate CAM checks before using it
for fabrication.
