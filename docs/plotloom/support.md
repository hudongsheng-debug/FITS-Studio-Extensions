# PlotLoom Support

Turn numerical data into clear scientific figures on your Mac.

Contact: [hudongsheng356@gmail.com](mailto:hudongsheng356@gmail.com)

## Requirements

PlotLoom requires macOS 14 or later and supports Apple Silicon and Intel Macs. It runs independently; neither MATLAB nor FITS QuickLook Studio is required.

## Get started

1. Click **Load Demo** to explore the built-in numerical example, or **Open MAT / FITS…** to open a local data file.
2. Choose your **Y data / table column**. Use **Browse data hierarchy…** to expand cell/struct containers or search for a numeric field. Full paths also appear in the X and error selectors.
3. Enter Y series such as `1,2,3`. Series numbers start at 1. Matrix columns normally become series; **Use matrix rows as series** transposes this mapping. MAT row and column vectors are treated as one series. Fixed-vector FITS columns retain one table row per sample.
4. Choose a chart type, adjust its mapping, and edit the title, axis labels, grid, legend, and line width.
5. Export as **PNG**, **PDF**, or **SVG**. PNG output is 2200 × 1520 pixels; PDF and SVG use vector graphics.

## Choose the right chart

- **Line / Scatter:** compare selected Y series with an X variable or row index.
- **Error bars:** select a matching error variable and column. Values are nonnegative absolute, symmetric Y uncertainties; the selected error column is shared across plotted series. PlotLoom does not calculate those uncertainties for you.
- **Grouped bars:** compare series within each row, up to 100 rows.
- **Box plot:** summarize each series using quartiles, median, 1.5 × IQR whiskers and separately displayed outliers. Quartiles use linear interpolation.
- **Polar:** use automatic angles or a selected angle variable. Angles default to radians; supplied angles may be interpreted as degrees. Radius must be nonnegative.
- **Complex plane:** plot the real component on X and imaginary component on Y.
- **Nonzero pattern:** show nonzero matrix coordinates, with column on X and row on Y. Row numbers increase downward. Sparse storage is preserved, including for very large dimensions; an empty sparse matrix displays an empty coordinate range.

## Complex and sparse data

For complex input, choose real part, imaginary part, magnitude, or phase in radians. Component selectors are available for complex Y, X, and error data. A complex-plane plot uses the selected Y data's real and imaginary components directly.

Sparse matrices retain nonzero coordinates instead of becoming full dense matrices. Ordinary charts extract only the selected series and include implicit zeros. The nonzero-pattern view supports up to 50,000 nonzero entries.

## Multidimensional data

MAT v7.3 and FITS images can expose additional axes. Choose a one-based index for axis 3 and later to read a two-dimensional plane. Supported arrays have up to eight dimensions. If the same dataset is used for multiple mappings, its slice selection is shared. No automatic WCS transformation or spectral-axis calibration is performed.

## Supported files

**MAT v5–v7.2 / Level-5:** two-dimensional numeric and logical leaves, complex matrices, sparse matrices, and numeric leaves inside nested cell/struct containers, including struct arrays. Compressed data and both byte orders are supported. Container indices follow MATLAB's column-major linear ordering.

**MAT v7.3 / HDF5:** supported numeric/logical arrays, standard real/imag complex storage, MATLAB sparse groups, cell references, and struct fields/references. Common deflate-compressed datasets are supported. External links/storage and third-party HDF5 filters are not loaded.

**FITS:** image HDUs, selected multidimensional planes, gzip files and supported tiled compression; ASCII and binary numeric table columns, fixed-length vector columns, and binary complex columns. Image BSCALE/BZERO and table TSCAL/TZERO are applied. Null values become nonfinite values and are omitted from plots. Available table units are displayed, not automatically converted. Rice tiled compression and gzip are included in automated tests.

MAT text, objects/custom classes, FITS text/bit/logical columns, and FITS P/Q variable-length columns are not offered for plotting. This is not a MATLAB runtime: `.m` scripts and `.fig` files are not supported.

## Limits and numerical details

- Level-5 MAT files: up to 32 MiB; dense matrices up to one million values. Real/imaginary values and sparse coordinates together are limited to two million imported items per file.
- MAT v7.3 / FITS: up to 512 MiB; whole-file gzip output must also fit within 512 MiB. Dense slices or table columns contain at most one million values.
- Sparse inputs: up to one million stored entries and one million columns, with bounded row dimensions. Full matrix storage is not allocated.
- Catalogs: up to 256 numeric datasets, bounded container traversal and up to 16 nesting levels.
- Charts: up to eight series and 50,000 selected values; grouped bars support up to 100 rows. Data are not silently downsampled.
- Values are represented as Double. Integers beyond 2^53 may not be represented exactly. Plot values must have magnitude below 1e100. Previously quantized FITS data cannot regain lost precision during reading.

## Troubleshooting

**A variable or column is missing:** check whether it is numeric and uses a supported format. Text, custom objects, unsupported filters and variable-length table columns are not selectable. Empty dense MAT leaves may not be listed.

**The chart shows a mapping error:** check the selected series numbers, orientation, and matching X/error sample counts. Error magnitudes must be nonnegative. Choose complex input for a complex-plane plot.

**Some samples disappear or a line has gaps:** NaN, infinity and FITS null samples are omitted. A nonfinite X or error value also excludes the corresponding sample. The figure footer reports omitted samples.

**A large file or plot is rejected:** reduce the file, slice dimensions, sample count, or selected series. Use Nonzero pattern for a large sparse matrix rather than requesting an extremely long dense series.

**The host app does not list PlotLoom:** PlotLoom remains usable directly. Its optional host entry depends on the host's extension catalog and publication status; it does not transfer the host's current matrix automatically.

## Report a problem

Email the app version, macOS version, file format/version, selected variable or column, chart type, and exact error message. When possible, include a small synthetic file that reproduces the issue rather than private research data. Do not send passwords or unrelated personal information.
