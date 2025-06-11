# Pilko Frame Capture Studio

**Pilko Studio** is a privacy-first, browser-based tool for extracting frames from your video files locally, offering a range of flexible extraction options. It works seamlessly on both desktop and mobile devices.

Try it here: https://landonikko.github.io/Pilko-Frame-Capture-Studio

**Offline Use:** Download `index.html` from this repository and open it in your browser. Core functionality works entirely offline, though the intended visual appearance relies on fonts and icons to be loaded via internet connection.

## ✨ Features
#### Upload a video
- Browser determines video format support. `.mp4`, `.webm`, `.mov` and `.avi` are usually well-supported. `.mkv` can fail on Firefox, but likely work on Chrome.

#### Display video metadata
- Resolution, duration, aspect ratio and bitrate.

#### Extraction mode | Manual
- Use the embedded video player to manually seek and  capture specific frames with the "Cut Frame" or "Save Frame" -buttons.

#### Extraction mode | Interval
- Capture screenshots at fixed time intervals (every 1–30s).

#### Extraction mode | Smart Auto
  - Use different frame comparison algorithms to capture only significant frame changes. [(1)](#underlying-concepts)
    - **Histogram Difference**<br />
        Compares the overall distribution of colors and brightness levels between frames. If the distribution is different enough (adjustable value) in a scene change, it triggers a frame capture. [(2)](#underlying-concepts)
    - **Pixel Difference**<br />
        Measures the percentage of pixels that have changed between frames. If the percentage is above the threshold (adjustable value), a frame capture will be triggered. [(3)](#underlying-concepts)

#### Contact Sheet
  - Generate a single image with a grid of evenly spaced thumbnails.  
  - Supports presets (5×4, 4×3) and custom grid sizes.  
  - Allows fine-tuning the frame capture positions before export via slider boxes, thumbnails and lightbox view.
  - Final image is generated at 3000px wide.

#### Output Configuration
- Choose to capture frames in PNG, JPEG or WEBP formats.
- Adjustable quality (1–100%) for lossy formats.
- Option to automatically remove black bars (for videos with baked-in letterboxing or pillarboxing). [(4)](#underlying-concepts), [(5)](#underlying-concepts)
  - Updates displayed metadata (resolution, aspect ratio) to match the cropped dimensions.

## 🖼️ Preview & Download
- Live preview of captured frames in grid and lightbox view.
- Manually remove unwanted frames.
- Hotkeys in lightbox view for efficient manual fine-tuning and validation.
- Download individual frames, ZIP archives or contact sheets.

## ⚙️🔒 Processing and Privacy
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
    Use Smart Auto Mode to generate training sets for AI models (e.g., LoRAs, Midjourney style references and moodboards).
- **Archivists / Content Managers**<br />
    Use Contact Sheet Mode to create a visual summary of the video — a quick reference without opening or scrubbing through the file.

## 📱 Mobile Ready
Fully functional on mobile browsers, allowing you to capture frames and create sheets directly on your phone or tablet. Great if you have a mobile-first workflow or don't have access to a desktop computer.

## 🗺️ Roadmap
The tool is mostly complete, but I still have ideas for improvements. I’m mainly thinking about making the Contact Sheet mode more extensive.
However, I want future updates to be **driven by user feedback**. If you can, please share how you use the tool and what you use it for (or want to use it for). It would help me better understand your core needs and implement those.

## 📣 Feedback
Please leave feedback by opening an Issue on GitHub.
You can also reach me at landonikko [at] gmail [dot] com

---
## 🤓 How it Works

**TL;DR:** Tool finds timestamps (or you pick them), your browser captures and processes the video frame at that time as an image and displays it to you.
	
1.  **Video Loading & Decoding:** Your browser's built-in media engine handles decoding the video file you select via the `<video>` element. The tool does not modify the original video.
2.  **Seeking:** When a frame capture is requested (manually or automatically), the tool instructs the `<video>` element to seek to the specific timestamp.
3.  **Canvas Rendering:** Once the browser indicates the video frame at that timestamp is ready, the tool draws the current visual state of the video onto a hidden off-screen `<canvas>` element using `drawImage`. This captures the pixels as rendered by the browser at that moment.
4.  **Black Bar Cropping (if enabled):** Before the final draw, the tool samples pixels near the edges of the frame (using `getImageData` on a temporary canvas draw) to detect solid black bars. If found, the coordinates for the `drawImage` operation are adjusted to only copy the active video region.
5.  **Image Encoding:** The pixel data on the final (potentially cropped) canvas is then encoded into your selected **Capture Format** (PNG, JPEG, or WEBP) using the `canvas.toBlob()` method, applying the chosen quality setting for JPEG/WEBP.
6.  **Blob Handling:** This process generates an image `Blob` (binary data). The tool creates temporary `Blob URLs` (using `URL.createObjectURL`) from these Blobs for displaying previews in the grid and lightbox. For downloads, these Blobs are either offered directly or packaged into a ZIP archive using the JSZip library.
7.  **Privacy:** At no point is your original video file or the generated image data uploaded to any external server.



1.  **Video Decoding:** Your browser uses its built-in video decoders (part of the HTML5 `<video>` element functionality) to decode the video file (`.mp4`, `.webm`, etc.) frame by frame as needed for playback or seeking. This decoding process happens internally within the browser based on the codecs inside the video file. The tool does not influence this decoding process or the video's native internal format.
2.  **Seeking:** When a frame capture is requested (manually, via interval, or smart detect), the tool tells the `<video>` element to seek to that specific timestamp (`video.currentTime = ...`).
3.  **Black Bar Detection (if enabled):** Before rendering the final frame, the tool briefly analyzes pixels near the frame edges (using `getImageData` on a temporary canvas draw) to detect solid black bars and determine the active video area coordinates (`cropX`, `cropY`, `cropWidth`, `cropHeight`).
4.  **Rendering to Canvas:** Once the video element has successfully seeked and the optional crop area is calculated, the tool uses the Canvas API (`ctx.drawImage(video, ...)`). This takes the visual representation of the video frame (using the calculated crop coordinates if enabled, otherwise the full frame) and draws those pixels onto a hidden `<canvas>` element. It's essentially taking a snapshot of the desired portion of what the video player would show.
5.  **Image Encoding (Capture Format):** This is where the user's selected **Capture Format** (PNG, JPEG, WEBP) and quality setting come into play. The tool calls `canvas.toBlob(callback, formatType, quality)`. The browser takes the raw pixel data currently on the canvas and encodes it into the specified image format, applying the appropriate compression (lossless for PNG, lossy for JPEG/WEBP with the chosen quality). The result is a `Blob` object containing the binary image data.
6.  **Storage/Display/Download:** This `Blob` is then used to create a temporary URL (`URL.createObjectURL`) for display in the preview grid/lightbox, or it's added to an array for later download (individually or in a ZIP archive using JSZip).

*(The separate "Processing and Privacy" section already covers the security aspects)*



codecs

## References and Underlying Concepts
1.  [Shot Transition Detection (Wikipedia)](https://en.wikipedia.org/wiki/Shot_transition_detection)
2.  [Histogram Comparison (OpenCV Docs)](https://docs.opencv.org/4.x/d8/dc8/tutorial_histogram_comparison.html)
3.  [Pixel Array Operations (OpenCV Docs)](https://docs.opencv.org/4.x/d2/de8/group__core__array.html#ga6dcfafa84b2c52094f606d362d04503d)
4.  [Letterboxing (Wikipedia)](https://en.wikipedia.org/wiki/Letterboxing_(filming))
5.  [Crop Detect Concept (FFmpeg)](https://ffmpeg.org/ffmpeg-filters.html#cropdetect) - *Note: Tool uses Canvas APIs, not FFmpeg directly.*
6.  [Canvas API (MDN)](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
7.  [Blob API (MDN)](https://developer.mozilla.org/en-US/docs/Web/API/Blob)

## Underlying Concepts
  1. [Shot Transition Detection (Wikipedia)](https://en.wikipedia.org/wiki/Shot_transition_detection)
  2. [Histogram Comparison (OpenCV Docs)](https://docs.opencv.org/4.x/d8/dc8/tutorial_histogram_comparison.html)
  3. [Pixel Array Operations (OpenCV Docs)](https://docs.opencv.org/4.x/d2/de8/group__core__array.html#ga6dcfafa84b2c52094f606d362d04503d)
  4. [Letterboxing (Wikipedia)](https://en.wikipedia.org/wiki/Letterboxing_(filming))
  5. [Crop Detect (FFmpeg)](https://ffmpeg.org/ffmpeg-filters.html#cropdetect)

## License

MIT License