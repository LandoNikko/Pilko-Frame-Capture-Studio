[![GitHub][github-shield]][github-url] [![License][license-shield]][license-url]   [![Email][gmail-shield]][gmail-url] ![Discord: landomrandom Status][discord-shield-static]

[github-shield]: https://img.shields.io/badge/GitHub-121727?style=for-the-badge&color=080c19&logo=github&logoColor=00c6ff
[github-url]: https://github.com/LandoNikko/Pilko-Frame-Capture-Studio

[license-shield]: https://img.shields.io/badge/License-MIT-121727?style=for-the-badge&labelColor=080c19&messageColor=e0e6f7&logo=gnu&logoColor=00c6ff
[license-url]: LICENSE

[gmail-shield]: https://img.shields.io/badge/Email-00c6ff?style=for-the-badge&color=080c19&logo=gmail&logoColor=00c6ff
[gmail-url]: landonikko@gmail.com

[discord-shield-static]: https://img.shields.io/badge/Discord-landomrandom-121727?style=for-the-badge&labelColor=080c19&messageColor=e0e6f7&logo=discord&logoColor=00c6ff

Pilko Studio is a frame capture web tool that lets you extract screenshots from your videos in many different ways, manually or automated, locally within your browser. It works seamlessly on both desktop and mobile.

Try it here: https://pilko.studio

Offline: Download `index.html`

<video src="https://github.com/user-attachments/assets/2eb13ce0-5c57-4d8f-aaad-a23820f57534" controls width="600"></video>

## ![Features Shield][features-shield]

- Example video for first testing.
- Video metadata display (resolution, duration, aspect ratio, estimated video bitrate).
- Capture format (PNG, JPEG, WEBP) and quality configuration (1-100%).
- Automatically remove black bars.
- Add text and/or timecode overlays.
- Capture methods
  - `Manual` - Navigate video player to capture and save specific frames.
  - `Interval` - Extract frames at regular intervals (frames or seconds).
  - `Smart Auto` - Automatically detects scene changes and aims to capture only one frame per scene.
  - `Grid` - Generates a grid of screenshots to a single image.
- Configure filenames for export.
- Preview frames in a gallery/lightbox, remove unwanted frames, download individually or as ZIP.
- Pro Mode - To support professional workflows
  - Set framerate for frame-accurate captures
  - SMPTE timecode overlay
  - Custom text overlay
  - Upload image/logo overlay

![Pilko_Panel](https://i.imgur.com/n5oZIt9.jpeg)

[features-shield]: https://img.shields.io/badge/Features-00c6ff?style=for-the-badge&color=121727

## ![Privacy & Processing Shield][processing-shield]

- No cloud processing or installations.
- Frames are stored temporarily in your browser.
- 100% client-side: built into a single `.html` using native HTML, CSS and JavaScript.
  - Why? For trust and accessibility. Easy to deploy locally, no installatiosn required.

[processing-shield]: https://img.shields.io/badge/Privacy%20&%20Processing-00c6ff?style=for-the-badge&color=121727

## ![Use Cases Shield][use-cases-shield]

- `thumbnails`
- `lecture screenshots`
- `visual notes`
- `design references`
- `mood board`
- `film analysis`
- `AI dataset building`
- `Midjourney style references`

[use-cases-shield]: https://img.shields.io/badge/Use_Cases-00c6ff?style=for-the-badge&color=121727

## ![How it Works Shield][how-it-works-shield] [![Try it][demo-shield]][demo-url]

The tool finds timestamps (or you pick them). Your browser's built-in capabilities (`<video>`, `<canvas>`) capture the frame at that time, optionally cropping based on black bar detection, encode it to the selected image format, and provide the image data for display/download.

The tool doesn't do video extraction from links, such as Youtube, TikTok, Instagram, etc.<br>
I recommend using [Media Download](https://github.com/mhogomchungu/media-downloader) or [Hitomi Downloader](https://github.com/KurtBestor/Hitomi-Downloader)

[how-it-works-shield]: https://img.shields.io/badge/How_it_Works-00c6ff?style=for-the-badge&color=121727

[demo-shield]: https://img.shields.io/badge/Try_it-00c6ff?style=for-the-badge&color=080c19
[demo-url]: [URL](https://pilko.studio)

## ![Feedback Shield][feedback-shield]

[![Email][gmail-shield]][gmail-url] ![Discord: landomrandom Status][discord-shield-static]

[feedback-shield]: https://img.shields.io/badge/Feedback-242c44?style=for-the-badge&color=121727&logo=github&logoColor=00c6ff