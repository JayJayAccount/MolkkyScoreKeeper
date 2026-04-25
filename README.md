# MÖLKKY Scorekeeper PWA

A fully offline-capable Progressive Web App for tracking Mölkky game scores on mobile devices. No browser bar, fullscreen experience optimized for Samsung Galaxy phones.

## Features

✅ **Offline First** - Works completely offline after first load  
✅ **Fullscreen PWA** - No browser chrome on mobile  
✅ **Progressive Web App** - Install directly to home screen  
✅ **Multi-player & Teams** - Support for 1-4 players or 2-4 teams  
✅ **Sound Effects** - Audio feedback for scoring (Web Audio API)  
✅ **Game History** - Track rounds and wins  
✅ **Mobile Optimized** - Fullscreen support for notch/safe areas  

## Installation on Samsung Galaxy Phone

### Option 1: Install as App (Recommended)

1. **Open in Chrome/Samsung Internet:**
   - Go to your GitHub Pages URL or local file
   - The app will prompt to install

2. **Install Prompt:**
   - Tap "Install Mölkky" banner
   - Or use browser menu → "Install app"

3. **Launch:**
   - App opens fullscreen without browser bar
   - Appears on home screen like native app

### Option 2: Add to Home Screen

1. **In Chrome/Samsung Internet:**
   - Open the app URL
   - Tap menu (⋮) → "Add to home screen"
   - Or use "Install app" option

2. **Offline Access:**
   - Once installed, all data is cached locally
   - Works without internet connection

## How It Works Offline

**First Visit:**
- App loads from CDN (requires internet)
- Service Worker caches all assets

**Offline Play:**
- Service Worker intercepts all requests
- Serves cached files automatically
- Game state saved in browser storage
- No internet needed to play

## File Structure

```
/
├── index.html              # Main app (fullscreen PWA)
├── manifest.json           # PWA metadata
├── service-worker.js       # Offline caching strategy
└── README.md              # This file
```

## Technical Details

**Manifest (`manifest.json`):**
- `display: "fullscreen"` - Removes browser bar on supported devices
- `orientation: "portrait-primary"` - Locks to portrait
- Multiple icon sizes for different devices
- App shortcuts for quick access

**Service Worker (`service-worker.js`):**
- Network-first strategy for live content
- Cache-first for assets after first request
- Automatic update checks (60-second intervals)
- Graceful offline fallback

**Mobile Optimization:**
- Safe area inset handling for notch/cutouts
- Status bar color matching (Samsung Galaxy)
- Touch optimization (no 300ms tap delay)
- Full viewport coverage

## Browser Support

✅ **Chrome/Chromium** (Android)  
✅ **Samsung Internet** (Recommended for Samsung devices)  
✅ **Firefox** (Android)  
✅ **Safari** (iOS - partial PWA support)  

## Game Rules (Mölkky)

- 12 pins numbered 1-12
- First to exactly 50 points wins
- Knock down 1 pin = score that pin's number
- Knock down 2+ pins = score count of knocked pins
- Miss 3 times = eliminated
- Going over 50 = reset to 25

## Troubleshooting

**App Won't Install:**
- Ensure you're using Chrome or Samsung Internet
- App requires HTTPS (except localhost)
- Clear browser cache and try again

**Offline Not Working:**
- First visit must be online to cache assets
- Check Service Worker status in DevTools
- Try: Settings → Apps → Clear Cache

**Score Not Saving:**
- Game saves automatically in browser memory
- Clearing app data will reset scores
- Use browser's Settings to manage storage

## Development

To serve locally:
```bash
# Simple HTTP server (any directory with index.html)
python -m http.server 8000
# Then open: http://localhost:8000
```

## License

Free to use and modify.

---

**Enjoy keeping score on the field!** ⚡🎯
