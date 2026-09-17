# LumaPair User Guide

## 1. Open a pair

Click **Open A…** (Command-O) and **Open B…** (Shift-Command-O) to choose FITS files. Alternatively, click **Load Demo** to explore the app without external files.

When both images have matching dimensions, LumaPair opens the shared canvas in Wipe mode. Images with different dimensions use a side-by-side fallback. Matching dimensions do not guarantee matching sky coordinates: register your images before comparison.

## 2. Reveal changes with Wipe

Select **Wipe**. Drag the vertical divider or the slider below the canvas to reveal image A on the left and image B on the right. Both views use the same display settings.

## 3. Observe changes with Blink

Select **Blink** to alternate between A and B. Adjust the interval from 0.15 to 2 seconds. Click **Pause** to stop alternation, then use **Toggle A / B** to switch manually. Click **Play** to resume.

## 4. Inspect overlap with Overlay

Select **Overlay**. Move the slider from A toward B to increase B's opacity. At 0%, only A is visible; at 100%, only B is visible. Intermediate values blend the rendered previews to help inspect overlap and visible displacement. This is a display blend, not subtraction of FITS pixel values.

## 5. Navigate the image

Drag the canvas to pan. Scroll or pinch to zoom. Double-click the canvas or click **Fit** to reset the view. In Wipe mode, drag away from the divider to pan rather than move the divider. Use the swap button between the file names to exchange A and B.

## 6. Set a common display

The Shared Display panel applies the same black point, white point, stretch curve, and palette to both images. Choose Linear, Asinh, or Logarithmic stretch, and Grayscale or Aurora color.

Initial display limits use the 1st and 99th percentiles of the combined valid preview samples. Displayed numerical limits include FITS BSCALE/BZERO scaling. **Reset Display** restores the default stretch, palette, and black/white positions within the current combined range.

Shared display settings do not normalize different exposure times or physical units. Calibrate those differences before interpreting brightness changes.

## 7. Supported data and limits

- macOS 14 or later; Apple Silicon and Intel.
- Uncompressed 2D primary images and IMAGE extensions, up to 512 MiB per file.
- BITPIX 8, 16, 32, 64, -32, and -64; BSCALE, BZERO, and integer BLANK handling.
- The first supported image HDU is read; its index is shown beside the file information.
- Previews use regular-grid sampling with a maximum dimension of 1024 pixels. Invalid values are excluded from display-range statistics.
- No automatic registration, compressed FITS, data cubes, full-resolution measurements, saved sessions, or report export.

Use original data and appropriate scientific tools to validate apparent changes. Small features can be lost during preview sampling.

All viewing operations run locally and leave your original files unchanged.

[Support](support.md) · [Privacy Policy](privacy.md)
