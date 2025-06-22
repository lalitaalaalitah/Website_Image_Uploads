# `05-creating-thumbnails.md`

## Step 5: Creating Thumbnails

For your main gallery page (the grid view), you don't want the browser to load a 1920px wide image and shrink it down. That's very inefficient. Instead, we'll create small, square-cropped thumbnails.

We will use the resized JPEGs in `01-resized-jpg` as the source for our thumbnails.

### The Command

This `ImageMagick` command is slightly different. It will resize, then crop the image to a perfect square to ensure a uniform grid.

```bash
# This command creates 400x400px square thumbnails,
# perfect for a gallery grid.

for file in 01-resized-jpg/*.{jpg,jpeg,JPG,JPEG}; do
  [ -f "$file" ] || continue
  filename=$(basename "$file")

  # Process the image with ImageMagick
  convert "$file" \
    -resize "400x400^" \
    -gravity center \
    -extent 400x400 \
    "03-thumbnails/$filename"

  echo "Created thumbnail for $filename"
done

echo "--- All thumbnails created. ---"
```

### Command Breakdown:
*   `convert "$file"`: The input file from our resized JPEGs.
*   `-resize "400x400^"`: The `^` symbol tells ImageMagick to resize the image so that it completely fills the 400x400 area, maintaining the aspect ratio. One dimension will be 400px, the other will be >= 400px.
*   `-gravity center`: Sets the focus for the next operation to the center of the image.
*   `-extent 400x400`: Crops the image to the specified dimensions (400x400) from the center.

The result is a folder full of perfectly uniform, small, and fast-loading thumbnails.
