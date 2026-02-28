# 📸 Live Camera Filters - PWA to APK

A professional camera application with 100+ live filters for stunning photos. This PWA can be converted to an Android APK.

## 🚀 Features

- 100+ professional camera filters
- Real-time filter preview
- Front/Rear camera switching
- High-quality photo capture
- Smooth, modern UI
- Offline support
- Mobile-optimized

## 📱 Convert PWA to APK

### Method 1: PWABuilder (Recommended - Easiest)

1. **Visit PWABuilder**
   - Go to [https://www.pwabuilder.com/](https://www.pwabuilder.com/)

2. **Enter Your URL**
   - Enter your GitHub Pages URL: `https://svyra-blackstring.github.io/Camara-/`
   - Click "Start"

3. **Generate APK**
   - Click on "Android" package
   - Choose "Trusted Web Activity" (TWA)
   - Configure settings:
     - App name: Live Camera Filters
     - Package ID: com.camfilters.app
     - Version: 1.0.0
   - Click "Generate"
   - Download the APK or AAB file

4. **Sign and Install**
   - Sign the APK with your keystore
   - Install on Android device

### Method 2: Bubblewrap CLI (Advanced)

```bash
# Install Bubblewrap
npm install -g @bubblewrap/cli

# Initialize project
bubblewrap init --manifest=https://svyra-blackstring.github.io/Camara-/manifest.json

# Build APK
bubblewrap build

# Install on device
bubblewrap install
```

### Method 3: Android Studio (Full Control)

1. **Create New Project**
   - Open Android Studio
   - Create "Empty Activity" project

2. **Add Trusted Web Activity**
   - Add dependency in `build.gradle`:
     ```gradle
     implementation 'com.google.androidbrowserhelper:androidbrowserhelper:2.5.0'
     ```

3. **Configure AndroidManifest.xml**
   ```xml
   <activity android:name="com.google.androidbrowserhelper.trusted.LauncherActivity">
       <intent-filter>
           <action android:name="android.intent.action.MAIN" />
           <category android:name="android.intent.category.LAUNCHER" />
       </intent-filter>
       <meta-data
           android:name="android.support.customtabs.trusted.DEFAULT_URL"
           android:value="https://svyra-blackstring.github.io/Camara-/" />
   </activity>
   ```

4. **Build APK**
   - Build > Build Bundle(s) / APK(s) > Build APK(s)

### Method 4: Capacitor (Hybrid App)

```bash
# Install Capacitor
npm install @capacitor/core @capacitor/cli
npx cap init

# Add Android platform
npm install @capacitor/android
npx cap add android

# Copy web assets
npx cap copy

# Open in Android Studio
npx cap open android

# Build APK from Android Studio
```

## 🌐 Deploy to GitHub Pages

1. **Enable GitHub Pages**
   - Go to repository Settings
   - Navigate to Pages section
   - Source: Deploy from branch `main`
   - Folder: `/ (root)`
   - Save

2. **Access Your App**
   - URL: `https://svyra-blackstring.github.io/Camara-/`
   - Wait 2-3 minutes for deployment

## 📋 Required Files Checklist

- ✅ `index.html` - Main app file
- ✅ `manifest.json` - PWA manifest
- ✅ `service-worker.js` - Offline support
- ⚠️ `icons/` - App icons (need to be created)

## 🎨 Creating App Icons

You need to create icons in these sizes:
- 72x72, 96x96, 128x128, 144x144, 152x152, 192x192, 384x384, 512x512

### Quick Icon Generation:

1. **Use Online Tools:**
   - [PWA Asset Generator](https://www.pwabuilder.com/imageGenerator)
   - [RealFaviconGenerator](https://realfavicongenerator.net/)
   - [Favicon.io](https://favicon.io/)

2. **Upload a base image** (1024x1024 recommended)
3. **Download generated icons**
4. **Upload to `/icons/` folder in your repo**

### Manual Creation:
```bash
# Create icons folder
mkdir icons

# Use ImageMagick to resize
convert base-icon.png -resize 72x72 icons/icon-72x72.png
convert base-icon.png -resize 96x96 icons/icon-96x96.png
convert base-icon.png -resize 128x128 icons/icon-128x128.png
convert base-icon.png -resize 144x144 icons/icon-144x144.png
convert base-icon.png -resize 152x152 icons/icon-152x152.png
convert base-icon.png -resize 192x192 icons/icon-192x192.png
convert base-icon.png -resize 384x384 icons/icon-384x384.png
convert base-icon.png -resize 512x512 icons/icon-512x512.png
```

## 🔧 Update index.html

Add these lines to your `<head>` section in `index.html`:

```html
<!-- PWA Manifest -->
<link rel="manifest" href="/manifest.json">

<!-- Theme Color -->
<meta name="theme-color" content="#000000">

<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/icons/icon-192x192.png">

<!-- Service Worker Registration -->
<script>
if ('serviceWorker' in navigator) {
  window.addEventListener('load', () => {
    navigator.serviceWorker.register('/service-worker.js')
      .then(reg => console.log('Service Worker registered'))
      .catch(err => console.log('Service Worker registration failed'));
  });
}
</script>
```

## 📱 Testing Your PWA

1. **Local Testing:**
   ```bash
   # Use a local server
   python -m http.server 8000
   # or
   npx serve
   ```

2. **Mobile Testing:**
   - Open Chrome DevTools
   - Toggle device toolbar (Ctrl+Shift+M)
   - Test responsiveness

3. **PWA Audit:**
   - Open Chrome DevTools
   - Go to Lighthouse tab
   - Run PWA audit

## 🔐 Permissions Required

The app requires these Android permissions:
- Camera access
- Storage access (for saving photos)

These are automatically handled by the PWA manifest.

## 📦 Distribution

### Google Play Store:
1. Create Google Play Developer account ($25 one-time fee)
2. Generate signed AAB (Android App Bundle)
3. Upload to Play Console
4. Fill in store listing details
5. Submit for review

### Direct APK Distribution:
1. Build signed APK
2. Host on your website
3. Users enable "Install from Unknown Sources"
4. Download and install

## 🛠️ Troubleshooting

**Camera not working in APK:**
- Ensure HTTPS is used (GitHub Pages provides this)
- Check camera permissions in manifest
- Test on actual device, not emulator

**Icons not showing:**
- Verify icon paths in manifest.json
- Ensure all icon sizes are created
- Check file names match exactly

**Service Worker not registering:**
- Verify service-worker.js is in root directory
- Check browser console for errors
- Ensure HTTPS is enabled

## 📄 License

MIT License - Feel free to use and modify

## 🤝 Contributing

Pull requests are welcome!

---

**Made with ❤️ for mobile photography**