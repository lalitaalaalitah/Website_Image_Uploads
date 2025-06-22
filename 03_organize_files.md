# `02-organize-files.md`

# Step 2: Organizing Your Project Files

A clean directory structure is crucial. It prevents you from accidentally overwriting your original high-resolution photos and keeps the different versions of your images tidy.

1.  Create a main project folder for your event. Let's name it `event-2024-gala`.
2.  Inside this folder, create a directory named `00-originals` and place all 300+ images from your photographer in here.
3.  Next, create the output directories where our scripts will save the processed images.

### Create the Directory Structure

Navigate to where you want to create your project folder in your terminal and run the following commands:

```bash
# Create the main project folder and navigate into it
mkdir event-2024-gala
cd event-2024-gala

# Create sub-directories for originals and processed images
mkdir 00-originals
mkdir 01-resized-jpg
mkdir 02-resized-webp
mkdir 03-thumbnails
```

Your final structure should look like this:

```
event-2024-gala/
├── 00-originals/      <-- Place your high-res photos here
├── 01-resized-jpg/    <-- Web-ready JPEGs will be saved here
├── 02-resized-webp/   <-- WebP versions will be saved here
└── 03-thumbnails/     <-- Gallery thumbnails will be saved here
```

**Action:** Move or copy all your original event photos into the `00-originals` directory before proceeding to the next step.
