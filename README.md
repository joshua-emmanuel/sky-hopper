# Sky Hopper

Sky Hopper is a 3D endless platformer built with Three.js. Hop between floating islands, steer around moving platforms, collect golden score orbs, and save hearts for an automatic midair revive.

## Play

Open `index.html` through a local web server. Because the game uses JavaScript modules, serving the folder over HTTP is more reliable than opening the file directly.

For example, from this directory:

```sh
python -m http.server 8000
```

Then visit <http://localhost:8000>.

## Controls

- **Desktop:** Hold **← / →** or **A / D** to steer.
- **Touch:** Hold the left or right half of the screen, or use the arrow hints.
- Land on islands to bounce and climb. Falling uses one stored heart for a rescue, if available.

Hearts grant revive stock (up to three). Gold score orbs award a random bonus from 20 to 1,000 points.

## Stylesheet development

Tailwind CSS v4 is built with PostCSS. Install dependencies and start the watcher to rebuild `tailwind.css` as you edit:

```sh
npm install
npm run css:watch
```

Before publishing, generate the final stylesheet with:

```sh
npm run css:build
```

Commit `tailwind.css` with `index.html`. The published game uses this generated file; it does not need Node.js or a build step at runtime. Three.js is loaded from the pinned import map in `index.html`.

## start.ng

The game supports the start.ng sign-in bridge when hosted on a supported start.ng domain. Guest play is available elsewhere. The local leaderboard and personal bests are stored in the browser.

For start.ng publishing requirements, see the [start.ng game documentation](https://start.ng/docs.md).
