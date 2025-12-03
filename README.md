# Merry Christmas Tree

An interactive holiday web scene built with Three.js and MediaPipe hand tracking.

The app turns a floating particle system into a glowing Christmas tree, lets you upload photos as ornaments, and supports webcam-based gesture control for switching between viewing modes.

## Live Demo

[https://tpppt.github.io/merry-christmas-tree/](https://tpppt.github.io/merry-christmas-tree/)

![Christmas Tree Preview](Christmas%20Tree.gif)

## Features

- Procedural 3D Christmas tree made from ornaments, dust particles, and lighting effects
- Image upload support so personal photos can appear on the tree
- Webcam preview with hand gesture detection powered by MediaPipe
- Three interaction modes: `TREE`, `SCATTER`, and `FOCUS`
- Keyboard fallbacks for hiding the UI and switching photos in focus mode

## Controls

### Upload

- Click `Add Memories` to upload one or more images

### Keyboard

- Press `H` to hide or show the upload controls
- In `FOCUS` mode, use `ArrowLeft` and `ArrowRight` to switch between photos

### Hand Gestures

- Open hand: switch to `SCATTER`
- Closed hand: switch back to `TREE`
- Pinch while in `SCATTER`: enter `FOCUS`
- Pinch again in `FOCUS`: cycle to the next photo
- Stay still for about 10 seconds in `FOCUS`: exit back to `SCATTER`

## Tech Stack

- [Three.js](https://threejs.org/) for rendering and post-processing
- `EffectComposer` and `UnrealBloomPass` for the glow effect
- [MediaPipe Tasks Vision](https://ai.google.dev/edge/mediapipe/solutions/vision/hand_landmarker) for hand tracking
- Browser `getUserMedia` for webcam access

## Run Locally

Because the project relies on ES modules, webcam access, and external CDN assets, it is best served through a local static server.

```bash
python -m http.server 8000
```

Then open `http://localhost:8000` in a modern browser such as Chrome or Edge and allow camera access when prompted.

## Project Structure

```text
.
|- Christmas Tree.gif
|- index.html
`- README.md
```

## Notes

- The project currently lives in a single `index.html` file
- Dependencies are loaded from CDNs through an import map
- A default festive placeholder image is generated when no user photos have been uploaded yet
