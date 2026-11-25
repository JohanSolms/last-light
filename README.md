# Last Light

*A desert walking (and driving) simulator.*

Just after sunset. Purple and orange sky, not a cloud. A lone highway runs through a wide semi-desert basin ringed by mountains, and somewhere ahead in the middle of nowhere a small gas station glows like an oasis.

You start in the car, near the end of the road, heading in. There is no goal. Drive, walk, look around.

## Running it

It's a single self-contained file: open `last-light.html` in a modern browser (Chrome, Edge, Firefox or Safari) and click **Begin**.

- It needs an internet connection the first time, to load Three.js and Tone.js from the jsDelivr CDN.
- Sound starts on the first click; browsers block audio until then.
- Headphones recommended.

To serve it locally instead of opening the file directly:

```bash
npx serve .
# or
python3 -m http.server
```

## Controls

| Action | Keyboard / mouse | Touch |
|---|---|---|
| Move / drive | WASD or arrow keys | Left thumb |
| Look | Mouse | Right thumb |
| Run | Shift | Run button |
| Jump / handbrake | Space | Jump / Brake button |
| Get in / out of the car | E | Car / Exit button |
| Speed limiter (60 km/h) on/off | L (in the car) | Lim button (in the car) |
| Walking camera 1st / 3rd person | V | Cam button |
| Dusk / starry night | T | Menu |
| Music on / off | M | Menu |
| Menu | Esc | ☰ |

The car always uses a third-person chase camera; when you get out you go back to your chosen walking view. If the browser blocks pointer lock, drag with the mouse to look.

## What's in it

**The world**
- About 4 km across: a desert basin with low dunes, flat-topped mesas and striped badlands rock, surrounded by mountains.
- A highway that curves out through mountain passes at both ends, with power lines and road signs.
- Flat-shaded low-poly style, with finer terrain detail near the player and coarser detail in the mountains.

**The gas station**
- A fuel canopy with one flickering, crackling tube, a "LAST CHANCE" pylon sign, a water tower and moths around the lights.
- A store you can walk into: stocked shelves, glowing fridges, a counter, a coffee station, buzzing lights and a door chime. Nobody's there.

**Places to find**
- A windmill and water trough, an old car wreck, a roadside cross, and a radio tower with a blinking red light.

**Wildlife**
- Foxes stop and watch you, then run off with a yip if you get close.
- Jackrabbits bolt, hawks circle overhead, tumbleweeds roll past.
- A lone coyote calls in the distance every few minutes.

**Sky**
- Dusk or starry night, switchable in game, with a full moon high overhead and a rare shooting star (about one every 5 minutes).

**Driving**
- Arcade handling with a capped turn rate for steady steering, six gears and a 60 km/h limiter that can be switched off (top speed about 110 km/h on the road).

## Sound

All audio is synthesised live; there are no audio files.

- **Music:** a slow, never-repeating generative soundtrack of pads, a reverby plucked guitar and a low drone, using Tone.js. It fades as you approach the station.
- **Car:** engine pitch follows revs and gears; tyre noise changes on dirt.
- **Footsteps:** different on sand, gravel, asphalt, concrete and the store's tile floor.
- **Ambience:** wind, crickets (louder at night), light buzz and fridge hum positioned in 3D; outside sounds muffle when you're indoors.

## Tech

- [Three.js](https://threejs.org/) r160 for rendering, with bloom post-processing (`UnrealBloomPass`).
- [Tone.js](https://tonejs.github.io/) 14.7 for music and sound.
- Procedural terrain from value noise; everything is generated in code at load time.
- Settings (time of day, camera, volumes, glow) are saved in the browser's localStorage.

## Performance

The terrain is around 400,000 triangles. If it runs slowly, turn **Glow** off in the menu (it's off by default on touch devices).

## Licence

Add your licence of choice here.
