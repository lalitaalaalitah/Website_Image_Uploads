# `01-setup-tools.md`

# Step 1: Installing Your Command-Line Tools

Before we can process any images, we need to install two essential, free, and open-source tools:

1.  **ImageMagick:** A robust suite for all-purpose image manipulation. We'll use it for resizing, compressing, and stripping metadata.
2.  **WebP:** Google's toolset for converting images to the highly efficient WebP format. We'll use the `cwebp` utility.

Open your terminal and run the appropriate command for your operating system.

### On macOS (using Homebrew)
If you don't have Homebrew, you can install it from [brew.sh](https://brew.sh/).

```bash
brew install imagemagick webp
```

### On Debian / Ubuntu
```bash
sudo apt update && sudo apt install -y imagemagick webp
```

### On Fedora / CentOS / RHEL
```bash
sudo dnf install -y ImageMagick libwebp-tools
```

### Verify Your Installation
After the installation completes, verify that the tools are available in your system's PATH by checking their versions.

```bash
# Verify ImageMagick
convert --version

# Verify cwebp
cwebp -version
```
If these commands output version information without errors, your tools are ready to use.
```
