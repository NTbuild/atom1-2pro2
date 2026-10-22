# atom1-2pro2 — Jo Mendes ring header

A loading animation that turns into the site's header, in one HTML file.

Project cards lay into a tumbling 3D ring one after another while the counter climbs. At 100% the light rises from below, the camera dives inside the ring and it becomes a row of big curved screens on one shared circle, behind the header: the **Jo Mendes** wordmark, the nav, and Prev / Visit this project / Next along the bottom. The front screen fills most of the width and its neighbours bleed off the sides.

Open through a local server (three.js and the textures won't load from `file://`). Press `R` to replay the intro.
Browsing works like Studio Mirage (studiomirage.io): one scroll gesture moves one project on a spring (about half a second, a slight overshoot, settled in about a second), and the project's name settles across the middle of the front screen. Arrow keys, Prev / Next, dragging (a flick carries its momentum) and clicking a side screen also work.

The ring, the cloud bank and the warp are drawn with three.js (loaded from jsDelivr) in one WebGL canvas:
- each screen is a single curved mesh bent on the ring's circle in a shader, with rounded corners, a hairline edge and the sun's glare;
- the clouds are puffs cut from a generated sunrise photo (`assets/sky/puff-*.png`), each drifting, bobbing and breathing on its own, always in front of the screens;
- the finished frame goes through a fluid warp, the same technique Studio Mirage uses: a small stable-fluids simulation (velocity, divergence, pressure on the GPU), stirred by the pointer and by the ring as it travels, pushes every pixel by the fluid's velocity, with a slight colour split where it moves fast. Written from scratch here.

The background is plain eggshell with a soft light behind the front screen. The photos in `assets/gallery/` come from the tweakit media gallery. Fonts load from Google Fonts.
With reduced motion turned on, the page goes straight to the header and the clouds and warp hold still. Desktop only.

`prototypes/` keeps the earlier header explorations (three directions, plus light editions of each).

The loader concept was inspired by a reel from [@avi_vashishta29](https://www.instagram.com/avi_vashishta29/).
