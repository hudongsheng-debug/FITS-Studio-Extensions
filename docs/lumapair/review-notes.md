# App Review Notes

App: LumaPair
Apple ID: 6813025087
Bundle ID: com.greenjersey.LumaPair
Platform: macOS 14 or later
Contact: hudongsheng356@gmail.com

LumaPair is a standalone FITS image inspection app. No account, sign-in, subscription activation, external hardware, network connection, or installation of FITS QuickLook Studio is required to test the app. The app's current implementation has no in-app purchases.

## Suggested review steps

1. Launch LumaPair and click Load Demo. Two simulated images are provided in the app; no downloads are needed.
2. The app opens in Wipe mode. Drag the divider or the lower slider to inspect the added bright feature in image B.
3. Select Blink. Adjust the interval, click Pause, and use Toggle A / B to switch manually.
4. Select Overlay and move the opacity slider between A and B.
5. Adjust Shared Display controls. Both images use common black/white limits, stretch, and palette.
6. Drag to pan, scroll or pinch to zoom, and click Fit to reset.
7. Optionally use Open A… and Open B… to select supported local FITS images.

File access is limited by App Sandbox to user-selected files. Source images are not modified or uploaded. No analytics or tracking SDKs are included.

The app uses sampled previews up to 1024 pixels on the longest dimension. It does not perform automatic alignment, scientific difference measurements, or photometry. Wipe, Blink, and Overlay require images with matching dimensions; differing dimensions fall back to side-by-side viewing. Sessions are not persisted.

FITS QuickLook Studio integration is optional and consists of discovery and launching through its extension directory. LumaPair does not require the host or import an extension package. Its focus is single-canvas change inspection with Wipe, Blink, and Overlay; the host's existing Compare feature provides side-by-side viewing and synchronized navigation.
