# Travel Agency Website

This is a modern, 3D-style responsive travel agency website built with Next.js, Tailwind CSS, GSAP, and Framer Motion. 

## How the Hero Section Scroll Effect Works

One of the coolest features of this website is the "video scrub" scroll effect in the hero section. Here is a simple, plain-English breakdown of exactly how it happens:

1. **The Sticky Pin**
   When you land on the page and start scrolling down, the entire hero section "pins" itself to the screen. It becomes sticky, meaning the page stops scrolling down normally, and you stay locked in the hero section for a little while.

2. **Tracking the Scroll**
   Even though the screen is pinned, the browser still tracks how far you *would* have scrolled. We use an animation library called GSAP (GreenSock) to measure this scroll progress from 0% to 100%.

3. **The Canvas Flipbook**
   Instead of playing a real video file (which is heavy and hard to control with scrolling), we use a `<canvas>` element. We took a video and exported it into exactly 197 individual picture frames. 
   
   Think of the canvas like a flipbook. As you scroll down (increasing that 0% to 100% progress), the code flips through the images one by one. If you scroll to 50%, it shows image #98. If you scroll backward, it plays the images in reverse. 

4. **The Text and Search Widget**
   While you are flipping through these images, that same 0-100% scroll progress is used to control other things on the screen:
   * First, the main "Explore the World" text is told to quickly slide up and fade out so it gets out of the way of the video.
   * Then, right at the very end of the scroll (from 80% to 100%), the Search Widget is told to slowly fade in and slide up from the bottom.

5. **Unpinning**
   Once you reach 100% of the pinned scroll distance, the hero section finally "unpins", and you seamlessly scroll down into the rest of the website (the Explore Escape section)!

---
### Running the Project

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.
