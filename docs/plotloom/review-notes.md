# PlotLoom — App Review Notes

PlotLoom is a standalone macOS scientific plotting app. No sign-in, review account, MATLAB installation, companion app, or external service is required. The plotting workflow works offline.

Quick review:
1. Launch PlotLoom and click Load Demo.
2. The demo selects observations as Y and theta as X. Y series 1,2,3 displays three series.
3. Use Chart type to try Line, Scatter, Error bars, Grouped bars, Box plot, and Polar. The demo includes an uncertainty variable for error bars.
4. Change the title, labels, grid, legend, or line width. Use Export to save PNG, PDF, or SVG to a location you choose.

Additional data features:
Use Open MAT / FITS to select a local file. Browse data hierarchy expands supported numeric leaves within MAT cell and struct containers. For complex data, select Real part, Imaginary part, Magnitude, or Phase (radians), or use Complex plane. Sparse matrices can be shown as a Nonzero pattern without expanding the whole matrix. Multidimensional MAT v7.3 and FITS images provide slice controls. FITS ASCII and binary numeric table columns can be mapped to X, Y, and error values.

Optional review fixtures are in the accompanying PlotLoom-Review-Examples.zip attachment:
- matlab-v7.mat and matlab-v73.mat: nested containers, complex data, sparse matrices and an empty sparse matrix. Choose z for complex plots or huge for a sparse nonzero pattern.
- tables.fits: choose the MEASUREMENTS flux column as Y, series 1,2; time as X; and error for Error bars. The second time value is intentionally null.
The six basic chart types can be reviewed using Load Demo without these attachments. Complex plane and Nonzero pattern are two additional chart types.

Supported formats are bounded subsets, not full MATLAB compatibility. MAT objects/custom classes, text, and FITS variable-length columns are not plotted. MAT Level-5 numeric leaves are currently limited to two dimensions. The app does not execute MATLAB scripts.

File access is user initiated. Parsing and rendering occur locally; the app contains no advertising, tracking, or analytics SDK. The file read/write entitlement supports opening user-selected data and saving exports. Reading does not modify the input file.

PlotLoom can optionally be launched from FITS QuickLook Studio's extension catalog, but it operates independently and does not require the host app.

Review contact: hudongsheng356@gmail.com
