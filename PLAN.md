# PLAN: "MonsterTube"

A horror game with jump scares and puzzles. It runs in a web browser, all in one `index.html` file.

---

## 1. The Story

You're an urban explorer YouTuber on the MonsterTube channel. Tonight you're sneaking through a dark forest and an abandoned science lab to film clips good enough to win subscribers.

**Get the shots, get subscribers, stay alive.**

**Opening cutscene** (after a "🎧 Tap to begin" screen that turns the sound on; before the menu; **Skip** button bottom-right; the locked door **rattles**, then you **bang on it** three times, and the street scene has **rain sounds** while you look straight down the road): (all in first person; **you're white** (light skin, set by `player.skinColor`), **you see your own hands** in every scene: holding a tax bill, trying the door, fists at your sides as you walk, holding your phone (only your thumbs show; fingers are behind it), thumbs typing on an on-screen keyboard; but NOT in the last scene, where you are not there) you're broke in an old house with tax bills all over the floor → the bank locks you out (the door is chained and padlocked with an eviction notice; your hand tries the knob) → you walk the city streets at night → you open MonsterTube and see people make a living from these videos → you search "most haunted place" (with **typing sounds**) and find St. Mercy Forest → a ghost and two **scary hooded figures** appear (tall ragged robes, black faces with glowing eyes, bony claws); the ghost asks one of them **"Is he perfect?"** and it answers **"Yes… he is."** → the menu.

### What happened at the lab (everything is connected)
1. **The Rift.** The lab built a machine to open a tear into "somewhere else." It worked too well. Something came through: the **Ghost**, which now drifts through the forest.
2. **The AI.** To contain the rift, the scientists built an AI bot that could talk, plan and copy human voices and texts. It decided the humans were the problem. It became the **Mimic**.
3. **The Serum.** To power the rift machine, the lab tested a growth serum on animals. A spider got into the serum tanks and grew huge. It lives in the tunnels and is the **Spider**.
4. The staff fled overnight and the company covered it all up. The rift machine is still humming in the basement.

### Your best friend: the tech genius
- Name: **Dex** (editable in SETTINGS).
- Stays home, hacks maps for you, finds door codes and texts you tips.
- **Always types with perfect spelling, capitals and punctuation.** That's the main way to spot the Mimic.
- Mimic clues: a typo, a wrong detail (wrong nickname, wrong pet name, wrong channel name), or a text that arrives when you have **0 signal bars**.

---

## 2. The Phone (in your hand)

You walk around in first person (W/S or ▲▼ to walk, A/D or ◀▶ to turn). Your phone is in your hand:
- **Phone down**: you see the dark world with your own eyes. Monsters like the Ghost are invisible.
- **Phone up** (Space or 📱): you see through the camera. The Ghost shows up on the phone screen. The glowing screen adds a little danger.
- **Jump scares fill your whole screen**, not just the phone.

Apps you can switch between using a bottom app bar:

### 📷 Camera (the main explore view)
- Top bar: **battery %**, **signal bars**, **red REC dot** (blinks while recording).
- Buttons: **Flashlight** (on/off), **Record** (start/stop), and arrows to look and move.
- **Danger meter** (bar on the side).
  - Flashlight ON: drains battery and fills danger.
  - Recording ON: drains battery and fills danger.
  - Both OFF: safe and slowly cools down, but the screen is nearly black. You can only **listen** (sounds and on-screen captions like *"whispers…"*).
  - Danger fills to 100% and the area's monster comes, which means a jump scare.
- Battery: it never runs out (it can be turned back on in SETTINGS with `battery.neverDies: false`).

### ▶️ MonsterTube
- Shows **subscribers**, **money**, and your **clip list** (uploaded ✅ or not ❌).
- **Upload** only works with enough signal bars (set in SETTINGS).
- **Clips you haven't uploaded are lost if you get caught.**
- Reaching subscriber goals pays **money**.
- **Shop** (spend money):
  - Bigger battery
  - Power bank (one-time battery refill, can buy several)
  - Night vision (see in the dark with the flashlight off, but it drains a little battery)
  - Signal booster (+1 signal bar everywhere)

### 💬 Messages
- Texts and calls from Dex, **or the Mimic pretending to be Dex.**
- Notifications make a sound, which matters in the Spider tunnels (see below).

### 🎮 Games (new)
- Opens a list showing **1 game: "Bat Dash"**.
- **Bat Dash** is a tap-to-fly game (the same kind as Flappy Bird, with our own art). You tap or press Space to flap a little bat up through gaps between dead trees. Gravity pulls it down, and touching a tree or the ground ends the run.
- Shows **Score** and **Best** (your record).
- **Rewards:** when you **set a new record**, you get a reward:
  - money for the Shop (amount in SETTINGS, for example $5 per point above your old best, up to a cap), and
  - a "NEW RECORD!" banner.
- The catch: the phone screen glows, so **playing raises danger** just like any app. Playing in a safe spot is fine, but playing near a monster is risky. Bat Dash also pauses automatically if a jump scare happens.
- The best score is saved between runs (browser storage).

### Screen glow rule
Any app that isn't the Camera adds a **small amount of danger per second** (amount in SETTINGS). It's bigger in "dangerous spots."

---

**Controls:** W/S walk, A/D turn, Shift sprint, **Space jump**, **P phone**, F flashlight, R record, K key, C crouch, Esc pause.

## 3. The Monsters

(All monsters use dark, dirty, bloody colors: the ghost's dress is stained and bloody, the spider is near-black and hairy with a skull marking and dripping fangs, the final monster has dirty grey skin, yellow teeth, red gums and blood.)

| Monster | Where | How it works | Jump scare |
|---|---|---|---|
| **Ghost** | Forest, trail, tower | A pale woman in a ragged white dress, with long black hair over her face and one glowing red eye. **Only visible through the phone camera.** **Totally silent** until the jump scare. When she's close, **your signal drops** and the camera glitches. **If she touches you, you get jumpscared.** When the danger meter fills, she chases you. Lights off and phone down make her give up. She also rushes at you sometimes. **Shining your flashlight right at her stuns her for 8 seconds.** The flashlight flickers, worst when she's close. | Static flickers while she appears closer and closer in the real world, then her hair-covered face with the red eye fills the whole screen with a shriek. |
| **Mimic** | Lab entrance, main hall, lab rooms | Texts you **as Dex** to lure you into danger ("Go to Room B, the keycard is there!"). Following a fake text raises danger a lot or walks you into a trap. | A **fake video call from Dex**. You answer, Dex's face glitches, and it turns into the robot face with a distorted voice. |
| **Spider** | Basement and tunnels | Hunts by **sound**: footsteps, recording beeps, **phone notifications**. **Bright flashlight makes it back off** but drains battery fast. **Webs** alert it when you touch them. | **Legs creep over the top of the screen**, a pause, then it **drops down** into view with a hiss. |

---

## 4. The Map (in order)

1. **Forest Edge**: tutorial area. Learn the flashlight, recording and the danger meter. The first Ghost appears.
2. **Haunted Trail**: more Ghost activity. **Scavenger hunt** begins: find hidden **keypad code pieces**.
3. **Ranger Tower**: the only good **signal** spot in the forest, so upload here. Climbing the tower is a **platformer** section.
4. **Lab Entrance**: an old hospital (ST. MERCY HOSPITAL) **appears in the forest when you reach 1,000 subscribers**. A marker points to it. Its door creaks open when you walk up, and you can go inside (a dark ward with beds and flickering lights). **The ghost can't get inside**, so the hospital is a safe room. Stairs lead up to a **second floor** with more beds. **One light works on each floor.** Going inside makes the ghost stop chasing you until you go back out. On the 2nd floor there's a big glowing tube with a half-made monster, and **Dr. Voss**, who says: "I need the body pieces to make the monster. Can you help me?" **Body pieces:** when the hospital appears, **2 legs** (long, thick, dark and muscly with clawed feet) appear 18–32 steps around it. Walk up to one to pick it up. On **Easy** the legs glow yellow and the screen shows the distance and an arrow; on **Normal** it shows only the distance; on **Hard** you're on your own. **Bring both legs to Dr. Voss**: they go into the tube (the tube starts **empty**; now the legs float in it), he gives you the **basement key**, and his face turns sickly grey with dark circles under his eyes. Tap **🔑** (or K) to **hold the key** in your hand (a gold key with a big oval ring, square teeth, and "Da key" written on it). The **basement** is through a big, **bloody hatch** on the ground floor: you must be holding the key to open it. A ladder takes you down and back up. The basement is a **cave**, much bigger than the hospital (it reaches under the forest): rocky walls, a dirt floor, **stalactites** and **stalagmites**, boulders, **cobwebs**, and flickering bulbs dangling on wires. The first time you go down, a **cutscene** plays: you climb down and **drop the key** into the dark. You must **find the key** in the cave (it glints; on Easy it glows) to climb back out. The cave is **pitch black** and your **flashlight dies** down there. The **ghost can follow you down** and get you. **A huge spider lives in the cave**. Touching it = jump scare in every mode. Only on **Easy** can you see it (it glows). At **1,000 subs (Easy) / 1,500 (Normal) / 2,000 (Hard)** a subscriber climbs down and gives you **silent boots**: the spider can't hear you walk, run or jump. It can only **hear** you walking, and runs at you when you move; stop moving and it loses you. If it reaches you: **spider jump scare** (its legs grab you, lift you up, and shove you in its fanged mouth). **Easy:** press **C** (or 🧎) to crouch so it can't hear you, and the spider **glows**. **Normal:** you can crouch, but the spider is **invisible**. **Hard:** no crouching, invisible spider; it runs up, stops in front of you and **waits 2 seconds**: move and you die, stay still and it walks away. **2 arms** (long, thin, hooked, with clawed hands) are hidden in the cave, with the same per-mode hints as the legs. **Keypad puzzle**. Enter the code you found. The Mimic's first texts.
5. **Main Hall**: **power is out**. Scavenger hunt for **fuses** to restore it.
6. **Lab Rooms**: the Mimic hunts here. Find the **basement keycard**. Lots of fake texts.
7. **Basement Hatch**: the rift machine is visible. The Spider's territory starts.
8. **Tunnels**: Spider. Second **platformer** section: jump across pipes over webbed floors.
9. *(No escape or exit: the world is endless.)*

---

## 5. Puzzles

### Scavenger hunts
- **Keypad code (forest)**: 4 digits hidden around the Forest Edge, Trail and Tower. Some digits only show up **through the camera while recording** or **with night vision**. Dex texts you a hint for each.
- **Fuses (main hall)**: 3 fuses hidden in dark corners. Flashlight helps but raises danger.
- **Keycard (lab rooms)**: one keycard. The Mimic sends fake locations for it.

### Platformer sections (side-view, like a Scratch platformer)
- **Ranger Tower climb**: jump up broken stairs and ledges. Taking too long fills danger (the Ghost is circling).
- **Tunnel pipes**: jump across pipes. Landing on a web makes noise and alerts the Spider. Flashlight bursts push it back.
- The controls are simple: ← → to move and Space or ↑ to jump.

### Keypad
- At the lab entrance, enter the 4-digit code from the scavenger hunt. A wrong code beeps loudly and adds danger.

---

## 6. Clips and Subscribers

- **Every clip is worth the same number of subscribers** (one number in SETTINGS).
- You get a clip by **recording something interesting** (a monster, a clue, a weird event) for a few seconds while it's on screen.
- Each clip can only be counted once.
- Clips must be **uploaded** (enough signal) or they're lost if you get caught.
- Subscriber goals (for example 100 / 500 / 1,000) pay money for the Shop.
- **Live comments:** at **250 subscribers**, whenever your phone is up, the left side of the phone screen fills with comments: kind (green), mean (red), or saying it's fake (yellow).

---

## 7. The Ending

**Bring Dr. Voss both arms** (after the legs) → ending cutscene: he puts the arms and a body in the tube ("Where did you get that body?" "Oh… from a stranger."), then "By the way… I need your HEAD." He looks just like in the game, until **his face falls off like a mask**, showing he isn't human (chalky white, empty eyes, a huge grin); his limbs grow, he throws a knife and a **CATCH!** button appears: press it within **3 seconds** (or the screen goes black → menu); you catch it and throw it back, his head comes off and falls into the tube, the tube shatters and **the monster** (chalky white, empty eyes, a giant grin of teeth, pointy fingers and spiky claw toes) breaks out.
**Final chase:** the monster, the ghost and the spider all chase you in the forest (the ghost flickers in during the cutscene, and in the chase she is bigger and visible even without the phone). **Film all 3 within 5 seconds** (they run at you and reach you right when time is up) (each on camera ~1.5 s; too slow = the monster jump scare) → **helicopters** shoot them all and you get **8.3 billion MonsterTubers** → a **plane lands, you climb aboard and fly away** (looking out the window as the forest shrinks) → **YOU WIN**. Get caught → the monster's jump scare → menu.
**Checkpoints (per mode):** 🏥 the hospital appearing, 🕳 entering the cave, 👹 Dr. Voss turning into a monster. Reaching one saves it for that mode. Tapping a mode with checkpoints asks where to start (beginning or any reached checkpoint; others are locked). Start over erases them.
**Winning is the ONLY way to unlock modes:** win Easy → Normal, win Normal → Hard, win Hard → **credits** (Created by **Sully**, Artist & Tester **Augie**).

Getting caught (by the ghost or the spider) plays the jump scare, then **sends you straight back to the menu**.

---

## 7b. Modes

On **Normal and Hard** there's **no narration text at the bottom of the screen** (captions, cutscene narration); character dialog (speech bubbles, Dr. Voss, your own lines) still shows.

The start screen shows a huge **MONSTERTUBE** title and the mode buttons (no backstory or how-to text), plus a **🎮 Controls** button that shows the key list, and a **🎬 Credits** button. Under it, **🔄 Start over** (tap twice) erases all saved progress and plays the opening again. The pause screen shows the controls too. It has **Easy** (monsters ½ speed, hospital at 750 subscribers), **Normal** (hospital at 1,000), and **Hard** (monsters 2× speed, hospital at 1,500). A ⏸ button (or Esc) pauses, with **Resume** or **Exit to menu**. Sprinting depends on the mode: **Easy** = sprint forever, **Normal** = a sprint bar that drains and refills, **Hard** = no sprinting. When you die you can **Restart** (same mode) or go to the **Menu**. **You start with only Easy open. Normal is locked until you beat Easy, and Hard is locked until you beat Normal.** You beat a mode by winning the ending. The browser remembers which modes you've beaten.

---

## 8. How It's Built (simple tech)

- **One file: `index.html`**, containing the HTML, the CSS (`<style>`) and the JavaScript (`<script>`).
- **No libraries and no image files** to start. Everything is drawn with the HTML **canvas** (shapes, gradients, noise) and the sounds are made with the browser's **Web Audio** (beeps, static, whispers made from noise).
- **SETTINGS at the very top** of the script hold every piece of text and every number: battery drain, danger rates, clip value, prices, Dex's name, all text messages, Bat Dash gap size and reward. You can change the game without touching the code below it.
- The game runs in a loop about 60 times a second: **update** (meters, monsters), then **draw** (screen).
- **Scratch → JavaScript cheat sheet** (we'll use these ideas):
  - "when green flag clicked" → `startGame()`
  - "forever" → the game loop
  - "if … then" → `if (…) { … }`
  - variables → `let battery = 100;`
  - "broadcast" → calling a function like `showJumpScare()`

---

## 9. Build Order

Each step is small and playable before we move on.

### ✅ Step 1: First tiny version (DONE, then updated)
Update: you can walk around and raise/lower the phone, the Ghost is silent and looks like a long-haired ghost woman, the jump scare fills the whole screen, and uploading clips (with signal) earns **subscribers**.

Originally:
Only these things:
1. **Phone frame** on screen with the **Camera app**.
2. **Forest Edge** scene (dark trees drawn with code). Look left and right.
3. Top bar: **battery %, signal bars, REC dot**.
4. **Flashlight** and **Record** buttons that drain battery.
5. **Danger meter** that fills with light and recording and cools down when both are off.
6. **The Ghost**: visible only while recording, with whisper and static sound when off-camera. It drops your signal when close.
7. **One clip**: record the Ghost for 3 seconds, which gives "Clip saved!"
8. **One jump scare**: the Ghost's static-flicker scare when danger hits 100%, then a simple "CAUGHT" screen with a Restart button.

### Step 2: MonsterTube app
App switching, subscribers, the clip list, uploading with signal, losing unuploaded clips when caught, and the screen-glow danger.

### Step 3: Games app with Bat Dash
The Games button, a list with 1 game, Bat Dash itself, the best score, and money rewards for new records. Playing raises danger.

### Step 4: Shop
Money from subscriber goals and Bat Dash, plus the battery, power bank, night vision and signal booster upgrades.

### Step 5: Haunted Trail, Ranger Tower and the scavenger hunt
Moving between areas, keypad code pieces, the tower platformer, and uploading at the tower.

### Step 6: Messages app and Dex
Texts and hints from Dex, and notification sounds.

### Step 7: Lab Entrance, the keypad and the Mimic
Keypad puzzle, fake texts with clues (typos, wrong details, no-signal texts), and the Mimic's fake video call jump scare.

### Step 8: Main Hall and Lab Rooms
Fuse scavenger hunt, power restore, keycard hunt.

### Step 9: Basement, Tunnels and the Spider
Sound-hunting, flashlight push-back, webs, the pipe platformer, and the legs-over-the-screen jump scare.

### Step 10: Ending (done)
Arms → Dr. Voss → cutscene → chase → film all 3 → helicopters → win / unlock / credits.

### Step 11: Polish
Title screen, better sounds, screen shake, balancing the numbers in SETTINGS, and a save/continue option.
