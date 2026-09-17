# LumaPair Support

LumaPair helps you inspect changes between two FITS images using Wipe, Blink, and Overlay on a shared canvas. It runs independently; FITS QuickLook Studio is not required.

**Contact:** hudongsheng356@gmail.com

When requesting help, include your LumaPair version, macOS version, the steps that led to the problem, and any error message. For file-reading problems, include the file size, dimensions, and BITPIX value if available. Attach a sample only if you are comfortable sharing it.

## Quick answers

**How can I try the app without my own files?** Click Load Demo. The second simulated image includes a bright feature to make changes easier to see.

**Why are the comparison modes unavailable?** Open two supported FITS images with matching original dimensions. Different-size images are shown side by side as a fallback.

**Does LumaPair align images automatically?** No. Use registered images for meaningful Wipe, Blink, and Overlay inspection. Equal dimensions do not guarantee alignment.

**Why does a large image look pixelated when zoomed in?** Previews are sampled to a maximum dimension of 1024 pixels. Zoom magnifies that preview, not the full-resolution data.

**Why will a FITS file not open?** This version supports uncompressed 2D primary images or IMAGE extensions, up to 512 MiB per file. Compressed FITS and data cubes are not supported. The app reads the first supported image HDU.

**Are original files changed?** No. Viewing and display adjustments leave source files unchanged.

**Are sessions saved?** No. Reopen your files after restarting the app.

**How do I change the interface language?** Use the application's language setting in macOS and restart LumaPair. English, French, Spanish, German, and Simplified Chinese are supported.

[User Guide](user-guide.md) · [Privacy Policy](privacy.md)
