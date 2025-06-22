# `04-batch-convert-to-webp.md`

# Step 4: Batch Converting to WebP

WebP is a modern image format that provides superior compression and quality compared to JPEG. Serving WebP images can drastically reduce page weight. Most modern browsers support it.

We will now convert the resized JPEGs from `01-resized-jpg` into WebP format and save them in `02-resized-webp`.

### The Command

This loop uses Google's `cwebp` encoder, which is optimized specifically for this task.

```bash
# This command loops through the resized JPEGs and creates
# even smaller WebP versions.

for file in 01-resized-jpg/*.{jpg,jpeg,JPG,JPEG}; do
  [ -f "$file" ] || continue

  # Get the filename without the extension
  filename=$(basename "$file")
  base="${filename%.*}"

  # Convert to WebP using cwebp
  cwebp -q 75 "$file" -o "02-resized-webp/$base.webp"

  echo "Converted $filename to WebP"
done

echo "--- All images converted to WebP. ---"
```

### Command Breakdown:
*   `for file in 01-resized-jpg/...`: We loop through our already-optimized JPEGs.
*   `base="${filename%.*}}"`: This clever trick removes the file extension (e.g., `image.jpg` becomes `image`).
*   `cwebp`: The WebP conversion utility.
*   `-q 75`: Sets the quality factor for WebP (from 0 to 100). 75 is an excellent default.
*   `"$file"`: The input file (the JPEG).
*   `-o "02-resized-webp/$base.webp"`: The output file, with the new `.webp` extension.

After this step, you will have a full set of highly optimized WebP images ready for your gallery.
