# 🐾 Kitten Room

**A cute 3D kitten you can play with, right in your browser.**

### ▶️ [Play now: kitten-room](https://youssefagagg.github.io/kitten-room/cat.html)

Meet Ginger, a chubby little kitten who lives in a pastel playroom. She wanders around on her own, meows, chases the yarn ball and naps in her bed. You can tap buttons to make her jump, flip, dance and more. It's made for kids, and it's one HTML file with nothing to install.

## ✨ What you can do

- **Tap Ginger** and she meows, with a speech bubble.
- **Hover over her** (or tap on a phone) to pet her. Her eyes turn into happy `^ ^` curves and hearts float up.
- **Tap things in the room**:
  - 🧶 **Yarn ball**: she chases it, wiggles, and swats it across the rug
  - 🐟 **Food bowl**: a fish appears and she runs over to eat it
  - 🛏️ **Bed**: she curls up for a nap 💤, then wakes up with a big stretch
- **Turn on the 🔴 laser**: move your mouse or finger and she chases the red dot and pounces on it.
- **Press 🎨 Color**: switch between Ginger, Smokey, Bubblegum, Blueberry, Snowball and Midnight.
- **Drag** to look around the room, and **scroll or pinch** to zoom.

### Moves

| Button | What Ginger does |
|---|---|
| 🚶 Walk / 🏃 Run | Trots or gallops to a new spot |
| 🦘 Jump | Crouches, springs up, lands with a squish |
| 🤸 Flip | A full backflip in the air |
| 🌪️ Spin | Spins around twice mid-jump |
| 🎉 Dance | Stands on her back legs with a party hat 🎶 |
| 👋 Wave | Sits and waves, like a lucky cat |
| 🌀 Roll | Rolls over on the floor |
| 🧘 Stretch | Front paws forward, bottom up, big yawn |
| 🐈 Sit / 👅 Wash | Sits down, or licks a paw and washes her face |
| 🐾 Pounce | Wiggles her bottom, then leaps forward |
| 🧶 Play ball / 🐟 Feed / 😴 Nap | Same as tapping the ball, bowl or bed |

Every activity starts with a meow. Press <kbd>Space</kbd> to make her meow any time.

## 🚀 Run it

The easiest way is to open the live version: **https://youssefagagg.github.io/kitten-room/cat.html**. It works on computers, phones and tablets, so you can share the link with anyone.

To run it locally, open `cat.html` in a modern browser (Chrome, Edge, Firefox or Safari). That's all.

> **Needs an internet connection.** The 3D engine ([three.js](https://threejs.org/)) and the rounded font load from a CDN.

The live version is served by GitHub Pages from the `main` branch, so every push updates it within a minute or two. On small screens the buttons move into a swipeable bar at the bottom.

## 🛠️ How it works

Everything lives in `cat.html`: the page, the styles and one JavaScript module.

- **The kitten** is built from simple 3D shapes (spheres, capsules and cones) with toon shading and an outline effect, so she looks like a cartoon.
- **A small rig** of nested groups (hips, legs, neck, head and a chain of tail segments) lets the body bend, sit, stretch and flip.
- **The poses** are lists of numbers (leg angles, head tilt, tail curl, mouth open and so on). Each frame the code works out the pose it wants and eases the kitten toward it, so every move blends smoothly into the next. Walking and running move the legs based on the distance travelled, so the paws don't slide.
- **The behaviours** are small async functions that a new command can cancel. When nobody is playing, a "roam" loop picks things for her to do on her own.
- **The sounds** are made live with the Web Audio API. There are no sound files: each meow is a short tone whose pitch rises and falls.

### Make it your own

- **Add a fur colour:** add an entry to `PALETTES` with `fur`, `stripe` and `name`.
- **Change a pose:** edit the numbers in `POSES` (for example `sit` or `dance`) and refresh.
- **Add a move:** write a new function in `moves`, then add a button with `data-move="yourMove"`.

## 📄 License

[MIT](https://opensource.org/licenses/MIT): free to use, remix and share. Have fun! 🐱
