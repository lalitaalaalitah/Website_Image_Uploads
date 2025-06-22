# `03-batch-resize-and-compress.md`

## Step 3: Batch Resizing and Compressing JPEGs

In this step, we will process all images from the `00-originals` folder. Our command will do three things in one pass:
1.  **Resize:** Scale images down to a maximum width of 1920 pixels, which is perfect for most web displays.
2.  **Compress:** Set the JPEG quality to a reasonable level (e.g., 80) to reduce file size.
3.  **Strip Metadata:** Remove non-essential EXIF data (camera settings, location, etc.) to further shrink the file size.

Make sure you are inside your main project folder (`event-2024-gala`) in the terminal.

### The Command

This `for` loop will find every `.jpg` and `.jpeg` file in `00-originals` and process it.

```bash
# This command loops through all JPG files in the originals folder
# and creates an optimized version in the resized-jpg folder.

for file in 00-originals/*.{jpg,jpeg,JPG,JPEG}; do
  # Check if a file with the given extension exists
  [ -f "$file" ] || continue

  # Get the original filename
  filename=$(basename "$file")

  # Process the image with ImageMagick
  convert "$file" \
    -resize "1920x>" \
    -quality 80 \
    -strip \
    "01-resized-jpg/$filename"

  echo "Processed $filename"
done

echo "--- All JPEGs resized and compressed. ---"
```

### Command Breakdown:
*   `for file in ...`: A loop that iterates through all files matching the patterns (`.jpg`, `.jpeg`, etc.).
*   `[ -f "$file" ] || continue`: A safety check to prevent errors if no files match one of the patterns.
*   `convert "$file"`: Specifies the input file. The quotes handle filenames with spaces.
*   `-resize "1920x>"`: Resizes the image to have a maximum width of 1920px. The `>` ensures it only resizes if the image is *wider* than 1920px, preventing upscaling. Aspect ratio is maintained.
*   `-quality 80`: Sets the JPEG compression level. 75-85 is usually the sweet spot between quality and file size.
*   `-strip`: Removes all profiles and comments (EXIF, etc.).
*   `"01-resized-jpg/$filename"`: The output path and filename.

Run this command. It may take a few minutes depending on the number of images and your computer's speed.
