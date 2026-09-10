# The Binder Studio

A single-page tool for planning trading card binder layouts.
Everything runs in the browser. There is no backend and no build step.

## Files

    index.html          the whole application
    logo.png            header logo
    export-logo.png     mark stamped on exported and printed files
    watermark.png       watermark applied to downloaded PNGs
    favicon.ico         browser tab icon
    favicon.png         high resolution icon for bookmarks and phones
    .nojekyll           stops GitHub Pages from processing the folder
    _headers            security and caching headers (Netlify only)
    fonts/              self hosted webfonts

All paths are relative, so the folder works from a repository root,
a subfolder, or any static host.

## Deploying

Upload every file, keeping the fonts folder intact, to the root of the
repository. Use the upload option rather than creating files by hand:
the fonts and images are binary and will be corrupted if pasted.

## Replacing the artwork

Keep the filenames the same and the tool picks the new files up.
If a logo or watermark is missing, exports still work without it.

## Security headers

_headers is read by Netlify. It blocks framing by other sites, stops the
browser second guessing file types, limits referrer information sent to
third parties, and caches the fonts aggressively while keeping index.html
always fresh.

A content security policy is deliberately left off, because the Buy Me a
Coffee widget loads resources from domains that are not documented and a
policy written blind would be likely to break it. The file contains a
commented Report-Only line for working one out safely if wanted.

GitHub Pages ignores this file. It cannot set custom headers at all,
which is one reason to serve the site from Netlify or Cloudflare Pages.
