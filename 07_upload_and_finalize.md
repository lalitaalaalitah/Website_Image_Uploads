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

### Final Website Best Practices

To ensure your gallery is as fast as possible, implement these final steps on your website:

1.  **Choose a Lightweight Gallery Plugin:**
    *   Use a performance-focused plugin like **Modula**, **FooGallery**, or even the native WordPress Gallery Block. Avoid heavy page-builder galleries if possible.
    *   Configure your plugin to use your uploaded thumbnails for the grid view and link them to the full-size WebP images.

2.  **Enable Lazy Loading:**
    *   This is the most critical setting. It ensures only the images visible on the screen are loaded.
    *   Most modern performance plugins (like LiteSpeed Cache, often available on Hostinger) and gallery plugins have this feature. **Turn it on.**

3.  **Activate a CDN (Content Delivery Network):**
    *   A CDN serves your images from servers around the world, closer to your visitors. This drastically speeds up load times and reduces the load on your server.
    *   **Hostinger plans often include a one-click Cloudflare CDN integration. Activate it from your hPanel.** This is a huge, free performance win.

4.  **Consider Media Offloading (Long-Term):**
    *   As your site grows over the years, you can offload your media to a dedicated storage service like Amazon S3 or Bunny.net. This keeps your hosting account's disk space free and makes your site even faster. This is an advanced step for the future.

By following this complete workflow, you have created a professional, scalable, and extremely fast photo gallery that respects both your server's resources and your visitors' time.
