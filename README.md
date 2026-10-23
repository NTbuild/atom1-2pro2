# atom1-2pro2 — Jo Mendes ring header

A loading animation that turns into the site's header, in one HTML file.

Project cards lay into a tumbling 3D ring one after another while the counter climbs. At 100% the light rises from below, the camera dives inside the ring and it becomes a row of big curved screens on one shared circle, behind the header: the **Jo Mendes** wordmark, the nav, and Prev / Visit this project / Next along the bottom. The front screen fills 54% of the width and its neighbours bleed off the sides. The screens never rise into the header: every frame the ring drops just enough to keep each top edge below the wordmark and nav, wherever the pointer tilts it.

Open through a local server (three.js and the textures won't load from `file://`). Press `R` to replay the intro.
Browsing works like Studio Mirage (studiomirage.io): one scroll gesture moves one project on a spring (about half a second, a slight overshoot, settled in about a second), and the project's name is announced to screen readers (the screens carry their own type). Arrow keys, Prev / Next, dragging (a flick carries its momentum) and clicking a side screen also work.

The ring, the cloud bank and the warp are drawn with three.js (loaded from jsDelivr) in one WebGL canvas:
- each screen is a single curved mesh bent on the ring's circle in a shader, shaped like the glass of an old TV (big round corners, sides bowing out), no border; the clip bubbles with the glass: a strong bulge, a colour fringe that widens outward, heavy phosphor stripes and scanlines (faded on small, far screens), a glow round the bright parts, a rolling band, flicker and grain, the glass catching the light, and the sun's glare;
- the clouds are puffs cut from a generated sunrise photo (`assets/sky/puff-*.png`), each drifting, bobbing and breathing on its own, always in front of the screens and rising over their foot;
- the finished frame goes through a fluid warp, the same technique Studio Mirage uses: a small stable-fluids simulation (velocity, divergence, pressure on the GPU), stirred by the pointer and by the ring as it travels, pushes every pixel by the fluid's velocity, with a slight colour split where it moves fast. It rests in the header band, so nothing is smeared up behind the name. Written from scratch here.

The background is plain eggshell with a soft light behind the front screen. The screens play the four clips in `assets/tv/`, converted from references the client sent (the short "you gonna" loop slowed to a third of its speed). They are placeholders: check the rights before this goes public. Fonts load from Google Fonts.
With reduced motion turned on, the page goes straight to the header and the clouds and warp hold still. Desktop only.

`prototypes/` keeps the earlier header explorations (three directions, plus light editions of each).

The loader concept was inspired by a reel from [@avi_vashishta29](https://www.instagram.com/avi_vashishta29/).
