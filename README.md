# Ocraft — voxel sandbox

A browser voxel/Minecraft-style sandbox game in a **single HTML file** — no build step, no server, no internet needed. Open `index.html` (or the live page below) and play.

**▶ Play it live:** https://funkyfish49-ops.github.io/ocraft/

Ocraft ("oceans minecraft") is built on [jsminecraft](https://github.com/skurk/jsminecraft) by skurk, customized and extended with new gameplay (see below). The whole game — code, textures (procedurally painted), sounds (synthesized WebAudio), and three.js r186 itself (gzipped + base64, decompressed at startup) — lives inside the one HTML file.

## Features

**Base game** (upstream): infinite-ish voxel terrain with oceans and beaches, mining & building, crafting, day/night cycle, weather, hostile & passive mobs, tools, doors, water/lava, gamepad support, and a title screen with difficulty selection.

**Custom additions:**
- 🐉 **Dragons** — spawn in the wild, tame with dragon fruit, saddle and *ride* them (full 3D flight: W/S climb & dive, Space/Shift rise & sink), arm them with dragon armor; they breathe fire at threats. Hatch your own from craftable dragon eggs.
- 🐱 **Kittens** — cute painted-face cats that spawn in herds; feed a raw fish and they become your best friend forever (follow you, never despawn).
- 🤖 **Verity, your companion** — the friendly yellow AI-ball assistant that hops along at your side. Press **T** and just talk to it:
  - *"mine some diamonds"* (or gold, iron, copper, emerald, coal, lucky) — it glides off, phases to the nearest ore, and breaks it for you.
  - *"fight the mobs"* — it beats up the nearest hostile; name one (*"kill the zombie"*, *"attack the dragon"*) for a specific target.
  - *"give me something"* — random gifts (30-second cooldown, it has moods).
  - *"stop"*, *"who are you"*, say thanks… it answers everything, in its own way.
  - It counts down quietly all the while… and transforms into a tall hollow-eyed monster when night falls. Handle with care.
- 👩 **Niko** — beach-dwelling coconut thrower with a realistic painted portrait face.
- 🍀 **Lucky blocks** — rare gold "?" blocks; break one for 10 of a random gift. A solid 10×10×10 monolith of 1,000 lucky blocks spawns near you at game start.
- 🥚 **Spawn eggs** — one per mob (with a little fist icon), plus a craftable **mystery egg** (gold ore + chest) that hatches a random mob.
- 🎮 **Controller calibration** — any gamepad works, even weird ones. On the title screen, tap the 🎮 status chip (or just plug in a controller) to open **Controller Setup**: live button/axis monitor, plus a guided 18-step wizard (buttons, analog triggers, sticks, d-pad — even d-pads and triggers that hide on stick axes, like the Amazon Luna). Your mapping is saved per-controller in localStorage: calibrate once, it just works. Ported from Tournament Arena.
- ⛏️ **Furnace & smelting** (ores → ingots/gems with coal), full tool tiers (dirt → emerald) and **9 armor sets** with set bonuses — full lava set = fireproof, full water set = no drowning.
- 🪙 **Gold ore & chests**, and much more.

- 🌐 **2-player online co-op** — share one world with a friend on another machine, straight from the browser: WebRTC peer-to-peer, no server, no accounts. See below.

## Play with a friend (2 players, 2 machines)

The world seed is baked in, so both machines generate the identical terrain on their own — only your actions travel the wire.

1. Both of you open the same live page (the URL above) on your own machines.
2. Player 1: on the title screen click **Play with a friend → HOST A GAME** → copy the **link code** → send it to your friend (any chat app).
3. Player 2: click **Play with a friend → JOIN A GAME** → paste the link code → **CONNECT** → copy the **reply code** → send it back.
4. Player 1: paste the reply code → **CONNECT**. A moment later you're in one world: build together, fight mobs together, trade items by dropping them.

**What syncs:** both players (you see each other as little avatars with nametags), every block either of you places or breaks (the whole build history replays when Player 2 joins late), mobs (host-simulated — combat, taming, spawn eggs all work from either side), item drops & pickups, dragon riding (either player can ride; the dragon obeys whoever is on it), the day/night clock, and Verity — the T-chat works for both players, with the host running its brain and toasts shared.

**Notes & limits:** the connection is direct browser-to-browser via WebRTC (Google STUN for matchmaking); a few strict corporate/campus networks can block it. Thrown projectiles (skeleton arrows, coconuts, dragon fire) only hit the player on the host's screen. Villagers are local to each machine. If Player 2 disconnects, Player 1 keeps playing solo. Tip: test on the live GitHub Pages URL in a normal browser tab, not inside an embedded preview pane — pointer lock and clipboard copy work best there.

## Controls

Mouse + WASD as usual (pointer lock, or drag-look fallback), or any gamepad — standard pads just work, and anything odd can be taught via the built-in calibration wizard (title-screen 🎮 chip → Controller Setup → CALIBRATE). **T** opens the Verity chat. Full list in-game.

## License

- Game code: **GPL-3.0** (see [LICENSE](LICENSE)) — upstream jsminecraft © skurk, modifications © funkyfish49-ops. Full license texts are also embedded as comments at the end of `index.html`.
- three.js: MIT (© three.js authors) — [threejs.org](https://threejs.org)

## Credits

- [skurk/jsminecraft](https://github.com/skurk/jsminecraft) — the original game.
- [three.js](https://threejs.org) r186 — rendering (embedded).
