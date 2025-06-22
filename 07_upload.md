# `06-upload-and-next-steps.md`


## Step 6: Upload and Final Website Configuration

Congratulations! All the hard work is done. You now have three folders of optimized images, ready for the web:
*   `01-resized-jpg`: Fallback images for older browsers.
*   `02-resized-webp`: Your primary, high-performance gallery images.
*   `03-thumbnails`: Your fast-loading grid images.

### Uploading Your Images

While you can use the WordPress media uploader, for this many files it's often faster and more reliable to use an SFTP client (like [FileZilla](https://filezilla-project.org/) or [Cyberduck](https://cyberduck.io/)).

1.  Connect to your server via SFTP.
2.  Navigate to your WordPress uploads directory: `wp-content/uploads/`.
3.  Create a descriptive folder, for example, `events/2024-gala/`.
4.  Upload your `02-resized-webp` and `03-thumbnails` folders into it.

*Note: You may need a plugin like "Media from FTP" to register these files with the WordPress Media Library if your gallery plugin can't browse server folders directly.*
