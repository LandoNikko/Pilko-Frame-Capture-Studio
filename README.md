# Pilko Frame Capture Studio

**Pilko Studio** is a privacy-first, browser-based tool for extracting frames from your video files locally, offering a range of flexible extraction options. It works seamlessly on both desktop and mobile devices.

Try it here: https://landonikko.github.io/Pilko-Frame-Capture-Studio

**Offline Use:** Download `index.html` from this repository and open it in your browser. Core functionality works entirely offline, though the intended visual appearance relies on fonts and icons to be loaded via internet connection.

## ✨ Features
#### Upload a video

#### Display video metadata
- Resolution, duration, aspect ratio and bitrate.

#### Extraction mode | Manual
- Use the embedded video player to manually seek and  capture specific frames with the "Cut Frame" or "Save Frame" -buttons.

#### Extraction mode | Interval
- Capture screenshots at fixed time intervals (every 1–30s).

#### Extraction mode | Smart Auto
  - Use different frame comparison algorithms to capture only significant frame changes. [(1)](#references-and-underlying-concepts)
    - **Histogram Difference**<br />
        Compares the overall distribution of colors and brightness levels between frames. If the distribution is different enough (adjustable value) in a scene change, it triggers a frame capture. [(2)](#references-and-underlying-concepts)
    - **Pixel Difference**<br />
        Measures the percentage of pixels that have changed between frames. If the percentage is above the threshold (adjustable value), a frame capture will be triggered. [(3)](#references-and-underlying-concepts)

#### Contact Sheet
  - Generate a single image with a grid of evenly spaced thumbnails.  
  - Supports presets (5×4, 4×3) and custom grid sizes.  
  - Allows fine-tuning the frame capture positions before export via slider boxes, thumbnails and lightbox view.
  - Final image is generated at 3000px wide.

#### Output Configuration
- Choose to capture frames in PNG, JPEG or WEBP formats.
- Adjustable quality (1–100%) for lossy formats.
- Option to automatically remove black bars (for videos with baked-in letterboxing or pillarboxing). [(4)](#references-and-underlying-concepts), [(5)](#references-and-underlying-concepts)
  - Updates displayed metadata (resolution, aspect ratio) to match the cropped dimensions.

## Preview & Download
- Live preview of captured frames in grid and lightbox view.
- Manually remove unwanted frames.
- Hotkeys in lightbox view for efficient manual fine-tuning and validation.
- Download individual frames, ZIP archives or contact sheets.

## 🛠🔒 Processing and Privacy
- No cloud processing or installations.
- 100% client-side: built with HTML, CSS, and JavaScript.
- Frames are temporarily stored in your browser via Blob URLs and are cleared when you close the tab or clear the output.

## 🎯 Use Cases
- **Privacy-Conscious Users**<br />
    Process everything locally with no data ever leaving your device.
- **Content Creators**<br />
    Capture thumbnails or key moments for social media and video platforms.
- **Film Fans / Filmmakers**<br />
    Create contact sheets or capture specific scenes for analysis or inspiration.
- **Students**<br />
    Grab key screenshots from lectures or tutorials for notes, slides or study material.
- **Animators / Video Editors / VFX Artists**<br />
    Extract stills from video for storyboards, design references, thumbnails, visual planning or review.
- **AI Hobbyists**<br />
    Use Smart Auto Mode to generate training sets for AI models (e.g., LoRAs, Midjourney style references).
- **Archivists / Content Managers**<br />
    Use Contact Sheet Mode to create a visual summary of the video — a quick reference without opening or scrubbing through the file.

## 📱 Mobile Ready
- Fully functional on mobile browsers, allowing you to capture frames and create sheets directly on your phone or tablet. Great if you have a mobile-first workflow or do't have access to a computer.

## 🗺️ Roadmap
The tool is mostly complete, but I still have ideas for improvements. I’m mainly thinking about making the Contact Sheet mode more extensive.
However, I want future updates to be **driven by user feedback**. If you can, please share how you use the tool and what you use it for (or want to use it for). It would help me better understand your core needs and implement those.

## 📣 Feedback
Please leave feedback by opening an Issue on GitHub.
You can also reach me at landonikko [at] gmail [dot] com

---
## Underlying Concepts
  1. [Shot Transition Detection (Wikipedia)](https://en.wikipedia.org/wiki/Shot_transition_detection)
  2. [Histogram Comparison (OpenCV Docs)](https://docs.opencv.org/4.x/d8/dc8/tutorial_histogram_comparison.html)
  3. [Pixel Array Operations (OpenCV Docs)](https://docs.opencv.org/4.x/d2/de8/group__core__array.html#ga6dcfafa84b2c52094f606d362d04503d)
  4. [Letterboxing (Wikipedia)](https://en.wikipedia.org/wiki/Letterboxing_(filming))
  5. [Crop Detect (FFmpeg)](https://ffmpeg.org/ffmpeg-filters.html#cropdetect)

## License

MIT License
