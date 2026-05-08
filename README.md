# GeoMetaName

A Windows desktop app for quickly inspecting metadata from one or many GeoTIFF files, without waiting for large multi-band rasters to fully load. View results in a table, export to CSV, and optionally save renamed copies using values extracted from metadata.

## Features

- Select GeoTIFF files (`.tif`, `.tiff`) from local folders.
- Add files in multiple rounds (e.g., from different folders) and keep appending to the table.
- Display essential GeoTIFF metadata in a table.
- (Optional) Look up the nearest city based on the raster extent center (requires internet).
- (Optional) Export the current table to CSV.
- (Optional) Save renamed copies of selected files using one-click formatted filenames based on chosen metadata fields.

## Metadata Fields

- File name
- File path
- Raster created date
- File size (MB)
- Column count / row count
- Pixel size (x, y)
- Pixel size unit
- Number of bands
- Band names
- Pixel depth (bits)
- Pixel data type(s)
- Extent in degrees (top/bottom latitude, left/right longitude)
- Geographic coordinate system
- Projection coordinate system
- Nearest city (optional, requires internet)

## How to Use GeoMetaName

### View metadata

1. Click **Add Files** and select one or more GeoTIFFs.
2. (Optional) Click **Add Files** again to add files from other folders.
3. (Optional) Enable **Lookup nearest city**.
4. Click **Show Metadata** to load and display metadata in the table.
5. After processing, you can choose to export to CSV.
6. You can also click **Save metadata as a csv file** at any time to export the current table.

### Save renamed copies (batch)

Use this to create copies of files with clearer, metadata-based names.

1. Click **Set Label** and enter a label for each file (recommended).  
   Labels help keep names meaningful and describe what the file represents.
2. Select the files you want to copy.
3. Choose which metadata fields to include in the new filenames.
4. Click **Save Renamed Copies** to generate copies with formatted names.

## Troubleshooting

- **Nearest city is empty / NaN**
  - Internet is unavailable, or the geocoding service cannot be reached.

- **Some metadata fields show `NaN`**
  - The source GeoTIFF does not contain that metadata (or it cannot be read).

- **Renamed copies have the same filename**
  - If multiple files have the same label and the same selected metadata values, the app will append a number to make filenames unique (e.g., `_1`, `_2`, ...).

## Credits

- **Author:** Xiangyu Ren
- **App name:** GeoMetaName

## Publish on GitHub (Binary-Only, No Source Code)

1. Create a new public repository on GitHub (for example: `GeoMetaName-App`).
2. Put only distribution docs in the repository:
   - `README.md`
   - `LICENSE`
   - `EULA.txt`
3. Do **not** upload source code files such as:
   - `GeoTIFF_metadata_app.py`
   - `GeoTIFF_metadata_app.spec`
   - `build_windows.ps1`
4. Build the executable locally:
   - `cd R:\geospatialToolsRX\RaterMetadata`
   - `powershell -ExecutionPolicy Bypass -File .\build_windows.ps1 -PythonExe python -SkipTkCheck`
5. Create a GitHub Release:
   - Open repo -> `Releases` -> `Draft a new release`
   - Tag example: `v1.0.0`
   - Title example: `GeoMetaName v1.0.0`
   - Upload `dist\GeoMetaName.exe`
   - (Optional) Upload a checksum text file
   - Click `Publish release`

## How Users Download the App

1. Go to your GitHub repository.
2. Open the **Releases** page.
3. Download `GeoMetaName.exe` from the latest release.
4. Run it on Windows (if SmartScreen appears, click `More info` -> `Run anyway`).

## License

This software is licensed as **freeware, closed-source** under the terms in `LICENSE`.
See `EULA.txt` for end-user terms when distributing the executable.
