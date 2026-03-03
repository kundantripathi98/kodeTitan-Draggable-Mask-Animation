# Draggable Video Mask Animation – Awwwards Style Rebuild

A premium draggable mask interaction built using **HTML, CSS, and Vanilla JavaScript**, powered by the **Canvas API** for real-time video sampling.

This project recreates a modern Awwwards-style illusion where multiple draggable panels appear to reveal a moving animated background — even though the video itself never moves.

---

## ✨ Features

- Multiple independent draggable mask containers  
- Real-time canvas video clipping  
- Accurate aspect-ratio scaling (object-fit: cover simulation)  
- Smooth rendering using `requestAnimationFrame`  
- Clean drag logic without external libraries  
- Mouse position HUD  
- Zero dependencies  

---

## 🛠️ Tech Stack

- HTML5  
- CSS3  
- JavaScript (ES6)  
- Canvas API  

No frameworks. No animation libraries.

---

## 🎥 Watch the Full Build

This project was rebuilt step-by-step on my YouTube channel.

👉 **Everyone Thinks This Awwwards Animation Is Complex — It’s Not**  
(https://youtu.be/FlSZfRot6DA)

If you enjoy premium UI rebuilds and animation breakdowns:

🔗 **KodeTitan**  
https://www.youtube.com/@kodeTitan

---

## 🚀 How It Works

### Hidden Video Strategy

The `<video>` element is:

- Set to 1px size  
- Fully transparent  
- Autoplaying in the background  

It acts purely as a pixel source.

The illusion works because the video never moves — only the sampling region changes.

---

### Aspect Ratio Matching

The script:

- Compares video and window aspect ratios  
- Calculates scaled dimensions  
- Offsets positioning  
- Maps viewport coordinates to video coordinates  

This manually recreates `object-fit: cover` behavior for perfect alignment.

---

### Canvas Sampling

Each mask:

1. Reads its current screen position  
2. Converts viewport coordinates into video coordinates  
3. Uses `drawImage()` to render the correct portion  

Core logic:

```js
ctx.drawImage(
  video,
  sourceX,
  sourceY,
  sourceWidth,
  sourceHeight,
  0,
  0,
  canvasWidth,
  canvasHeight
);
```

Continuous rendering is handled via `requestAnimationFrame()`.

---

### Drag System

Each mask:

- Stores position inside a `Map()`  
- Tracks cursor offset on `mousedown`  
- Updates position using `translate3d()`  
- Re-renders instantly  

Simple state. Clean structure.

---

## 📱 Responsive Behavior

- Masks use `vw` and `vh` units  
- Canvas dimensions sync with container size  
- Video scaling adapts to viewport ratio  

---

## 🔧 Setup

1. Clone or download the repository  
2. Place your video file as `video1.mp4` in the root folder  
3. Open `index.html` in your browser  

No build tools required.

---

## 📌 Notes

- Video must be muted for autoplay to work  
- Performance depends on video resolution  
- More masks = more canvas draw calls per frame  
- Designed as a motion-focused UI demo  

---

Built with clean logic and intentional math.
