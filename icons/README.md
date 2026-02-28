# App Icons

You need to create app icons in the following sizes and place them in this folder:

## Required Icon Sizes:
- icon-72x72.png
- icon-96x96.png
- icon-128x128.png
- icon-144x144.png
- icon-152x152.png
- icon-192x192.png
- icon-384x384.png
- icon-512x512.png

## Quick Icon Generation Tools:

### Option 1: PWA Asset Generator (Recommended)
1. Visit: https://www.pwabuilder.com/imageGenerator
2. Upload a 1024x1024 base image (camera icon recommended)
3. Download all generated icons
4. Upload them to this folder

### Option 2: RealFaviconGenerator
1. Visit: https://realfavicongenerator.net/
2. Upload your base image
3. Generate all sizes
4. Download and upload to this folder

### Option 3: Favicon.io
1. Visit: https://favicon.io/
2. Create or upload icon
3. Generate all sizes
4. Upload to this folder

### Option 4: Use ImageMagick (Command Line)
```bash
# Install ImageMagick first
# Then run these commands with your base image:

convert base-icon.png -resize 72x72 icon-72x72.png
convert base-icon.png -resize 96x96 icon-96x96.png
convert base-icon.png -resize 128x128 icon-128x128.png
convert base-icon.png -resize 144x144 icon-144x144.png
convert base-icon.png -resize 152x152 icon-152x152.png
convert base-icon.png -resize 192x192 icon-192x192.png
convert base-icon.png -resize 384x384 icon-384x384.png
convert base-icon.png -resize 512x512 icon-512x512.png
```

## Design Tips:
- Use a simple, recognizable camera icon
- Ensure good contrast
- Test on both light and dark backgrounds
- Keep it simple - icons are small
- Use PNG format with transparency
- Recommended colors: White icon on colored background or vice versa

## Temporary Solution:
Until you create proper icons, you can use a simple colored square as a placeholder. The app will still work, but won't look professional in app launchers.