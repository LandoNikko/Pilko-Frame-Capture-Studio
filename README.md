# Pilko Frame Capture Studio

**Pilko Frame Capture Studio** is a privacy-focused, web-based tool that lets you extract still frames (screenshots) from videos directly in your browser.

Try it here: https://landonikko.github.io/Pilko-Frame-Capture-Studio

---

## ✨ Features

**Upload a video**

- Works directly from your device or via browser drag-and-drop.

**Display video metadata**

- Shows resolution, duration, aspect ratio, and bitrate.

**4 Extraction Modes**

- **Interval Mode**  
  Capture screenshots at fixed time intervals (every 1–30s).

- **Smart Auto Mode**  
  Use frame comparison algorithms (Histogram, Pixel Diff, SSIM) to capture only significant frame changes.

- **Manual Mode**  
  Manually seek and capture specific frames using “Cut Frame” or “Quick Save Frame”.

- **Contact Sheet Mode**  
  Generate a single image with a grid of evenly spaced thumbnails.  
  Supports presets (5×4, 4×3) and custom dimensions.  
  Allows fine-tuning thumbnail positions before export.

**Output Configuration**

- Choose PNG, JPEG, or WEBP formats  
- Adjust quality (1–100%) for lossy formats  
- Automatically remove black bars (letterboxing/pillarboxing)

**Preview & Download**

- Live preview of captured frames in grid and lightbox view
- Manually remove unwanted frames  
- Download individual frames, ZIP archives, or contact sheets
- Hotkeys in lightbox for quick manual fine-tuning and validation  

---

## 🛠🔒 Processing and Privacy

- 100% client-side: built with HTML, CSS, and JavaScript  
- No server-side components or uploads  
- Frames are temporarily stored in your browser via Blob URLs

---

## 🎯 Use Cases

**Content Creators**  
Capture thumbnails or key moments for social media and video platforms.

**Video Editors / Animators**  
Extract stills from video for storyboards, design references, thumbnails, or visual planning.

**Archivists / Content Managers**  
Use Contact Sheet Mode to create a visual summary of the video — a quick reference without opening or scrubbing through the file.

**Students**  
Grab key screenshots from lectures or tutorials for notes, slides, or study material.

**AI Hobbyists**  
Use Smart Auto Mode to generate training sets for AI models (e.g., LoRAs, Midjourney style references).

**Film Fans / Filmmakers**  
Create contact sheets or capture specific scenes for analysis or inspiration.

**Privacy-Conscious Users**  
Process everything locally with no data ever leaving your device.

## 🗺️ Roadmap
The tool is mostly complete, but I still have ideas for improvements. I’m mainly thinking about making the Contact Sheet mode more extensive.
However, I want future updates to be driven by user feedback. If you can, please share how you use the tool and what you use it for (or want to use it for). It would help me better understand your core needs and implement those.

## 📣 Feedback
Please leave feedback by opening an Issue on GitHub.
You can also reach me at landonikko [at] gmail [dot] com

---

## License

MIT License
