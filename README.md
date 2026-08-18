# Reality Glitch Camera

Reality Glitch Camera is a single-page mobile web app for placing a 3D model over a live camera feed, manipulating it in real time, and recording the combined image in one continuous take. It was developed as a lightweight classroom tool for photogrammetry, digital/physical experimentation, and virtual-production concepts without requiring students to learn a full 3D or compositing package first.

## Features

- Live front/rear camera with optional mirroring
- Camera/lens selection when exposed by the browser
- Camera zoom when supported by the device
- Load **GLB/GLTF** or **OBJ + MTL + texture** photogrammetry models
- Touch controls for move, rotate, pinch-to-scale, and twist rotation
- Scale and opacity controls
- Adjustable virtual light color, intensity, direction, and ambient fill
- Optional manual ground-shadow catcher
- Still-image capture
- One-take WebM video recording with microphone audio
- **1080p recording by default**, with 720p and 540p alternatives
- Frame-rate choices generated from the selected camera's reported capabilities, up to 60 fps
- Runtime display of camera-input and live-render frame rates

## Quick Start

1. Open the page in a current mobile Safari or Chrome browser.
2. Tap **Start Camera + Mic** and allow permissions.
3. Tap **Load 3D** and select a model. For OBJ scans, select the OBJ, MTL, and texture images together.
4. Position and manipulate the model over the live camera image.
5. Open **Controls** to adjust recording quality, frame rate, lighting, perspective, opacity, or ground shadow.
6. Tap **REC** to make a continuous composited recording.

## Recording

The default recording setting is **1080p / 30 fps**. The app preserves the current screen aspect ratio, so "1080p" means a maximum output side of 1920 pixels rather than forcing every phone into a fixed 16:9 frame.

After camera permission is granted, the frame-rate menu is populated from the browser-reported capabilities of the selected camera. A phone may report support for a frame rate but be unable to combine it with a particular resolution; when that happens, the browser may fall back to a lower actual camera rate and the app records at that rate instead.

Use **720p** or **540p** for very dense scans or slower phones if rendering becomes uneven.

Recordings are saved as **WebM** using the best supported WebM codec exposed by the browser. No server-side transcoding is required.

## Limitations

The current page loads Three.js modules from jsDelivr, so an internet connection is required. For a fully self-contained/offline deployment, download the Three.js modules and update the import map to point to local copies.

This is **live 3D compositing**, not world-tracked AR. The virtual object is positioned relative to the camera image and does not automatically stay anchored to a real table, floor, or wall when the phone moves. There is also no automatic real-world depth occlusion. The ground shadow is manually positioned to help visually integrate a model into a shot.

Camera names, lens access, zoom ranges, frame rates, codecs, and recording performance vary by phone and browser. Test the intended classroom devices before relying on a particular feature.

## Privacy

Model files, camera video, microphone audio, still images, and recordings are processed in the browser and are not uploaded by this page. 

