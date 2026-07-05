# CARBON SKIRMISH

A single-level, browser-playable space battle built as a structural homage to CCP's
open-sourced Carbon engine: the code is split into a **Destiny** module (deterministic
fixed-tick world simulation — physics, AI, ballistics, waves) and a **Trinity** module
(rendering layer that reads sim state and never writes it), mirroring how `destiny` and
`trinity` divide responsibilities in the real stack. The actual Carbon repos are native
C++ and can't run in a web page, so this reimplements the architecture and EVE-style
mechanics in vanilla JS on a canvas — zero dependencies, one file.

## Play

Open `index.html` in any desktop browser. That's it.

Or play it live: **https://marcoakes.github.io/carbon-skirmish/**

## Host it on GitHub Pages

1. Create a new repo (e.g. `carbon-skirmish`) and add `index.html` and this README.
2. Repo → Settings → Pages → Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → Save.
3. After a minute the game is live at `https://<your-username>.github.io/carbon-skirmish/`.

## How to play

You are the **Fleet Commander** of a five-ship wing — two tackle frigates (Talon,
Grip), two destroyers (Hammer, Anvil), and the logistics cruiser Mercy, who keeps
everyone repaired. **Your fleet shoots whatever target you lock** — call targets
like an FC. Broadcast orders on **1–4**: focus fire, defend me, free engage, regroup.
Enemy waves bring their own logistics ("Menders") that repair their fleet —
**always primary the logi first**, like every EVE FC ever taught.

The title screen shows every control, and your first flight walks you through them
step by step. **P** pauses and brings the control reference back at any time.

- **WASD** — thrust. Your ship is a space battleship in the spirit of the *Yamato* —
  she keeps her inertia and swings her bow slowly; feather it.
- **Shift** — afterburner (drains capacitor).
- **Space (hold)** — the **WAVE MOTION GUN**. Needs a full capacitor, slows you while
  charging, then erases everything in a 2.6 km corridor ahead of the bow. Long recharge.
  Aim it by flying — the ship fires where the bow points.
- **Tab / click a hostile** — begin target lock. Once locked, turrets fire automatically
  when the target is inside 520 m.
- Shield recharges, armor doesn't, hull is your life. Damage flows shield → armor → hull.
- Capacitor powers guns and afterburner and regenerates over time. Run it dry and you
  can't shoot.
- **Speed is armor.** Turrets have tracking: the faster your transversal, the more
  enemy shots miss. Sit still and everything hits you.
- **Webifier frigates** slow you to half speed at close range — kill them first.
- The cruiser's heavy turrets track slowly: get close and orbit fast to slip under her
  guns. Her **torpedoes** home in on you — outrun them with the afterburner or cut
  perpendicular at the last moment.
- Clear all three waves — scouts, frigates, then the cruiser **Sanguine Vesper** and
  escorts — to secure the site. **R** restarts.

## License

MIT — see [LICENSE](LICENSE).
