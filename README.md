# PushBlock - Pushup Blocker Chrome Extension

A Chrome extension that blocks distracting websites until you complete a set number of pushups, with AI-powered pushup detection using computer vision.

## How to run? (locally)
   - Start the server (run pushup_counter.py)
   - Go to chrome://extensions/
   - Turn on "Developer Mode" (top right corner)
   - Select "Load Unpacked" (top left corner)
   - Select the extention folder
   - Begin your pushup journey!

## Project Structure

```
PushBlock/
├── extension/           # Chrome extension files
│   ├── manifest.json    # Extension manifest
│   ├── background.js    # Service worker for blocking logic
│   ├── popup.html       # Extension popup interface
│   ├── popup.js         # Popup functionality
│   ├── blocked.html     # Blocked site page
│   ├── blocked.js       # Pushup tracking interface
│   └── images/          # Extension icons
│       ├── icon16.png
│       ├── icon48.png
│       └── icon128.png
├── server/              # Python Flask server
│   ├── pushup_counter.py # Main server with AI pushup detection
│   └── requirements.txt  # Python dependencies
├── assets/              # Media assets
│   └── subwaysurfers.mp4 # Background video for blocked page
├── docs/                # Documentation
│   └── project.txt      # Project description and notes
└── README.md           # This file
```

## Features

- **Website Blocking**: Blocks distracting websites (YouTube, Reddit, Facebook, etc.)
- **AI Pushup Detection**: Uses MediaPipe and OpenCV for real-time pushup counting
- **Customizable Requirements**: Set the number of pushups required to unblock sites
- **Temporary Access**: 30-minute access after completing pushups
- **Visual Feedback**: Real-time pushup tracking with camera feed

## Setup Instructions

### Chrome Extension

1. Open Chrome and go to `chrome://extensions/`
2. Enable "Developer mode"
3. Click "Load unpacked" and select the `extension/` folder
4. The extension will be installed and ready to use

### Python Server

1. Navigate to the `server/` directory:

   ```bash
   cd server/
   ```

2. Install Python dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Run the server:
   ```bash
   python pushup_counter.py
   ```

The server will start on `http://localhost:5001`

## Usage

1. **Configure Blocked Sites**: Click the extension icon to add/remove sites to block
2. **Set Pushup Requirements**: Configure how many pushups are required (default: 10)
3. **Access Blocked Site**: When you try to visit a blocked site, you'll be redirected to the pushup page
4. **Complete Pushups**: Use the camera to track and complete the required pushups
5. **Gain Access**: After completing pushups, you'll have 30 minutes of access to the site

## Technical Details

- **Frontend**: Chrome Extension (HTML, CSS, JavaScript)
- **Backend**: Python Flask server with MediaPipe for pose detection
- **Computer Vision**: OpenCV and MediaPipe for real-time pushup tracking
- **Storage**: Chrome extension storage API for settings persistence

## Dependencies

### Chrome Extension

- No external dependencies (uses Chrome APIs)

### Python Server

- Flask
- Flask-CORS
- OpenCV (opencv-python)
- MediaPipe
- NumPy
- Pillow

## Development

The project is organized into clear folders for easy development:

- `extension/` - All Chrome extension files
- `server/` - Python Flask server and dependencies
- `assets/` - Media files and resources
- `docs/` - Documentation and project notes

This structure makes it easy to work on different parts of the project independently and maintain clean separation of concerns.
