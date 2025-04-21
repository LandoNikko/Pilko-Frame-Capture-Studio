# Nia Frame Capture Studio

**Nia Frame Capture Studio** is a privacy-focused, web-based tool that lets you extract still frames (screenshots) from videos directly in your browser.

---

## ✨ Features

- **Upload a video**.
- **Display video metadata**: resolution, duration, aspect ratio, bitrate.
- **3 Extraction Modes**:
  - **Interval Mode**: Capture screenshots at fixed time intervals (every 1-30s).
  - **Smart Auto Mode**: Use different frame comparison algorithms (Histogram, Pixel Diff or SSIM) to capture only significant frame changes.
  - **Manual Mode**: Manually seek and capture specific frames using "Cut Frame" or "Quick Save Frame".
  - **Contact Sheet Mode**: Generate a single image with a grid of evenly spaced thumbnails.
    - Supports presets (5x4, 4x3) and custom dimensions.
    - Allows fine-tuning thumbnail positions before export.
- **Output Configuration**:
  - Automatically remove black bars (letterboxing/pillarboxing).
- **Live preview** of all extracted frames and manual removal.
- **Download options**:
  - Choose PNG JPEG,or WEBP.
    - Adjust image quality for lossy formats (from 1% to 100%).
  - Download individual frames.
  - Batch download as ZIP.
  - Export contact sheet as a single image.

---

## 🛠🔒 Processing and Privacy

- Everything works completely in the browser using HTML, CSS and JavaScript with no cloud or server-side dependencies.
- Each captured frame is assigned with temporary Blob URLs, which are stored in your browser's local cache.

---

## 🎯 Use Cases
- **Content Creators**: Capture thumbnails or key moments for social media and video platforms.
- **Video Editors / Animators**: Extract stills from video for storyboards, design references, thumbnails, or visual planning.
- **Archivists / Content Managers**: Use Contact Sheet Mode to create a visual summary of the video. A quick reference without opening or scrubbing through a video file.
- **Students**: Grab key screenshots from lectures or tutorials for notes, slides or study material.
- **AI Hobbyists**: Use Smart Auto Mode to generate training sets for AI models (e.g., LoRAs, Midjourney style references).
- **Film Fans / Film Makers**: Create contact sheets or capture specific scenes for analysis or inspiration.
- **Privacy-Conscious Users**: Process everything locally with no data ever leaving your device.

## License

MIT Licence