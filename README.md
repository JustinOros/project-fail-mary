# Project Fail Mary

A zero gravity co-op and competitive ship repair game that runs in the browser. Float around a broken spaceship as a five legged crawler, grab walls, push off, patch the damaged areas, then power the reactor with Astrophage before the ship self destructs.

Play it: https://justinoros.github.io/project-fail-mary/

No install, no server, no account. It is a single `index.html` file.

The start screen shows how many games have been played. Each time a lobby starts a new game from level 1, the host's browser adds one to a public counter on the free Abacus service (abacus.jasoncameron.dev). No names or lobby codes are sent. If the service is unreachable the line is simply hidden.

## Playing with friends

1. One player opens the page, sets a name and color, and clicks **Play**. That opens a lobby with just them in it.
2. Click the clipboard button to copy an invite link and send it to friends.
3. Friends click the link, pick a name and color, and click **Join**. Each friend taps **I am ready** in the lobby, and the host sees a checkmark next to everyone who is loaded and ready. The host can still start early by pressing Start twice. They can also open the page, type the 4 letter code, and click **Join Lobby**.
4. The host clicks **Start**.

Press **Start** right away to play alone, or wait for friends to join first. To join a friend, click **Join**, type their 4 letter lobby code, and click **Join** again, or **Back** to return.

The host's lobby stays open while you wait. If the connection to the matchmaking server drops, the game reconnects by itself and keeps the same lobby code, so you do not need to make a new lobby.

Multiplayer uses free peer to peer connections (PeerJS). If someone cannot join, a strict network or firewall may be blocking direct connections. Try a different network or a phone hotspot.

## How a round works

- Patch every damaged area in the ship's walls. A wrench icon with a number blinks twice as you get close: that is how many wrenches it uses up. Wrenches are made on the 3D printer (see below). Everyone standing in the circle counts together, and more players patch faster.
- Damaged areas show glowing cracks spreading across the wall. The cracks grow longer and hotter as the damage gets worse, shrink while you repair, and fade away when the area is fixed.
- Patching a damaged area gives time back: 5 seconds per wrench it used, so a damage 3 area adds 15 seconds, shown as a green +15s. A patched hull breach adds 5 seconds. The timer can never go above the level's starting time.
- Small crews get extra time at the start of every level: 20 seconds when playing solo and 10 seconds with two players.
- From Level 3 on, damaged areas get worse over time (up to 3 wrenches). A spot at 3 that is ignored for 30 seconds bursts into a hull breach. Patching the breach repairs that damaged area for good. If the breach is not patched in time, the emergency bulkhead seals it and the area is damaged again.
- Once every damaged area is patched, the reactor wakes up inside a sealed dome. Each player has a switch outside the dome in their own color. Every active player must hold their own switch at the same time for about 2 seconds to open the reactor door. Once open, the door stays open.
- Glowing Astrophage (sparkle icon) drifts around the ship on its own from the start of the round. Fly into it to pick it up. Carry it into the dome and enter the reactor ring to deliver it. When enough Astrophage has been delivered (shown as a counter), the reactor spends 3 seconds powering on, with a growing glow, shock rings and a shaking screen, and then the round is won. The amount needed grows with the level and is lower for small crews. If supply runs short, more Astrophage appears. While the reactor powers on, everyone still inside the dome does a little happy dance with smiling eyes, and then they are all blasted out through the door. Anyone who was in the room keeps dancing with happy eyes while the results show.
- A self destruct timer is running. If time runs out, the ship explodes and everyone loses.
- The ship's AI, Blip-A, talks to you in the broken, cheerful style of the alien engineer from Project Hail Mary (lines like "Amaze" and "Thank"). It speaks in a robot voice using your browser's built in speech and shows each line as a caption under the timer. It calls out fixed and critical damaged areas, hull breaches, debris storms, the self destruct countdown at 60, 30 and 10 seconds, repairs being complete, the reactor door, Astrophage deliveries, lost crew, and the end of the level. Turn the voice or the captions off in Settings. The Mute key silences the voice too.
- After each round a scoreboard shows everyone's points until the host starts the next level.
- There are 10 levels, and each one is bigger and nastier than the last.

## Scoring

| Action | Points |
| --- | --- |
| Power the reactor | 300 |
| Finish a damaged area | 60 |
| Help patch a damaged area | 40 |

## Moving around

You float in zero gravity, so momentum is everything.

- Hold **grab** next to a wall to stick to it. Hold grab next to a friend and a short tether connects you. While you keep holding grab the tether keeps you close, and either of you can pull the other around with thrusters or by pushing off walls. Let go of grab and the tether snaps.
- Release grab to push off toward where you are aiming. Holding grab longer before releasing gives a harder push.
- Thrusters give you extra control, but fuel is limited and does not refill on its own.
- Repairs start by themselves while you are inside the dashed ring around a panel. No button is needed. If you leave the ring for more than 1 second, or get stunned, the progress resets back to zero.
- Fuel boxes refill half a tank. Just fly into one. A box is ignored while your tank is almost full, so it stays for someone who needs it.
- Crawlers bump into each other, so you can knock a friend off a panel.
- If a breach sucks you out, you respawn at an airlock as a downed crawler with X eyes and cannot move or act. Any teammate can revive you by staying inside your dashed circle for about 3 seconds, and more helpers revive you faster. Grabbing a downed friend tethers them to you so you can drag them and stay in range. If nobody is left standing, the ship reboots you automatically after about 6 seconds.

## Inventory and tools

- The row of slots at the bottom of the screen is your inventory. New items go into the first free slot.
- Select a slot with the number keys 1 to 9, the mouse wheel, a click, or LT and RT or left and right on the D-pad. The selected item is equipped and shown in your crawler's hand.
- Drop the selected item with Q, right click on a slot, or X on a controller. Dropped items float away, and anyone can pick them up by touching them. You cannot pick your own drop back up for about a second and a half.
- Wrenches and the printer are heavy. Every heavy item you carry makes your thrusters weaker, lowers your top speed, weakens your push off, and burns fuel faster. Throwing items is a quick way to pass them to friends.

## 3D printer, filament and keycards

- Every player has their own 3D printer, which they carry like any item. It is heavy and cannot be dropped or thrown. On Levels 1 and 2 everyone also starts with one wrench.
- Filament floats around the ship like fuel. Touch it to pick it up. Anyone can carry it, and you can throw it to a friend who needs it.
- Printing is automatic. Stand in a damaged area circle or a breach with gray filament and no wrench, and your printer makes a wrench (2 seconds) which is then used on the repair. Touch a locked door while carrying filament of its color and the keycard is printed and the door opens. Players in the same circle do not print more wrenches than the spot needs.
- A banner at the bottom tells you what you are missing, for example "A wrench is required to repair this damage (1 Gray Filament)." or "A Blue keycard is required to open this door (1 Blue Filament)."
- Press E (Y on a controller or phone) to open the print menu. It lists what you can print, with the cost under each name: a wrench (1 gray filament), a keycard of each color you have filament for (1 filament of that color), and fuel (1 Astrophage refills your whole tank). Items you cannot afford are greyed out and say what is missing. The most useful item for where you are standing is listed first. Tap or click a row, press its number (1 to 9), or use the D-pad, LT and RT to pick one and press A, X or Y to print it. B closes the menu. Each print takes 2 seconds. Burning an Astrophage for fuel costs the crew one, and a replacement slowly respawns, so only do it when you are low.
- When your fuel is low and you carry an Astrophage, a button appears above your inventory. Tap or click it to burn 1 Astrophage for a full tank in one step.
- The print menu can also make a Flashlight, Gravity Boots and a Magnet, 2 gray filament each. They are never printed automatically, so you have to open the menu. You can hold one of each at a time. Select the item in your inventory to use it; a newly printed one is selected for you.
- Flashlight: when loose Astrophage is nearby, it selects itself, lights up the area and pulls the Astrophage toward you so it is easy to collect. You can still select another item and it stays off until Astrophage comes into range again.
- Recycle: select a printed item in your inventory, open the print menu and choose Recycle. It is returned as filament right away: a wrench or a keycard gives 1 filament of its color, and the Flashlight, Gravity Boots and Magnet give 2 gray. On a phone, tap the item in the bottom bar first, then tap Recycle.
- Magnet: it works as long as you carry it, with no need to select it. Loose filament within a short distance drifts toward you, and fuel boxes can be collected from farther away, with a blue stream showing the pull. Drop it to turn it off.
- Gravity Boots: they work as long as you carry them, with no need to select them. Five small boots show on your feet. Drop them to take them off. When you are close to a wall they pull you onto it and you can walk along it by pushing the stick, arrow keys or phone stick in the direction you want to go. You do not need to hold Thrust. Hold Grab and release to jump off and fly. They have no fuel limit for now.
- Wrenches can be dropped and passed to friends. Damaged areas and hull breach patches (2 wrenches) use them up.

## Colored doors and keycards

From level 2 on, some doorways between rooms are sealed with a colored lock. Filament of the same color is lying somewhere in the ship, always in a part you can reach before that door. Print it into a keycard on the 3D printer.

- Carry the keycard and touch the matching door to unlock it for everyone. The keycard is used up.
- Keycards can be dropped and passed to friends like any other item.
- Locked doors are shown on the minimap in their color.

## The Blip-A

The ship you are repairing is the Blip-A, and it is slowly rotating clockwise. From inside it looks like a real spacecraft: riveted hull plating with portholes, deck plating on the floor, a curved nose with a cockpit window and a blinking antenna, three glowing engines at the stern, and fins and pods along the top and bottom. These are only for looks and do not change how you move. Outside, a red planet, a tethered research spacecraft and a spacewalking astronaut drift past the hull in the other direction, so you can always tell the ship is spinning.

## Tutorial hints

New players get short tips as they play, with a gold arrow and ring pointing at what to do next: aiming, grabbing a wall, launching, finding a panel, repairing, low fuel, keys and doors, and the final repair. Each tip shows once, and the button labels match your device (keyboard, controller or touch).

Open the cog and use **Tutorial hints** to turn them off. Turning them back on makes every tip show again.

## Hazards

Hazards ramp up as levels go on: electric orbs, steam vents, slick walls you cannot grab, debris storms, black holes that suck you out and respawn you, and lights out darkness.

## Controls

| Action | Keyboard and mouse | Controller |
| --- | --- | --- |
| Aim | Mouse, WASD or arrow keys | Left stick |
| Grab and push off | Space or left click | A or LB |
| Thrusters | Shift or right click | RB or B |
| Select inventory slot | 1 to 9 or mouse wheel | LT and RT, or D-pad left and right |
| Drop item | Q or right click a slot | X |
| Print on 3D printer | E or F | Y |
| Chat | Enter | Select or View |
| Mute | M | |

Click the cog at the top of the screen to rebind any keyboard key.

In menus on a controller, use the D-pad or stick to move, A to select, B to go back, and Start to confirm. Selecting the name or code box opens a built in on screen keyboard.

## Phones and tablets

Touch controls appear automatically on a touchscreen. Landscape gives the widest view, and the game adjusts when you rotate your phone.

- Drag anywhere on the left side of the screen to aim. Release to keep your last heading.
- The buttons on the right copy an Xbox controller: A grabs, B thrusts, X drops the selected item and Y prints. Hold them like the keyboard keys.
- With **Auto grab (touch)** on in the cog, which is the default, you grab a wall automatically as soon as you touch it. The A button then reads RELEASE: tap it to let go and push off, or hold it first to charge a stronger launch. Turn Auto grab off to grab only while you hold A, or tap A quickly to keep your grip until you tap it again.
- Tap a slot in the bottom bar to select an item.
- Tap the chat bubble next to the cog to type a message. Your phone keyboard pops up.

## Chat

Press Enter, or click the chat bubble next to the cog, in a lobby or during a game to type a message to everyone. On a controller, press Select or View to open the on screen keyboard, which includes a few emoji keys.

## Browser support

Works in current Chrome, Edge, Firefox and Safari. Xbox Edge works with a controller. The PlayStation browser may be unreliable.

## Hosting your own copy

The whole game is `index.html`. Put it in any static host, such as GitHub Pages, and it works. It must be served over HTTPS for multiplayer to connect.

## Spectating and rejoining

- If you join a lobby while a round is running, you watch instead of being turned away. Click, tap or press Q and E to switch between players, then press JUMP IN (or J) to spawn into the round.
- If you get disconnected, use the REJOIN button on the menu. You drop straight back into the round with your score kept.

## Sound

All sound is generated in the browser, so there are no audio files. A low engine hum and a gentle, echoing piano style melody over a repeating chord progression play while you are aboard the Blip-A. As the self destruct timer runs down the music adds a faster heartbeat, ticking, and finally an alarm beat. Once every area is repaired the music turns bright and hopeful for the reactor run. Effects include thruster hiss, wall thunks (heavier when you carry heavy items), a welding crackle while you repair, hull breach whooshes, printer whirrs, Astrophage shimmers, a reactor switch charge-up that rises as the crew joins in, and a door rumble. A beep speeds up as you get close to a damaged area, sparks crackle near damaged equipment, and the reactor hums as you approach. Sound goes muffled when you are sucked out or spectating. Settings has separate volume sliders for Master, Music, Sound effects, Alarms and warnings, and the Ship AI voice. The music dips while the ship AI talks. Mute with your mute key or the speaker button at the top of the screen. Your choices are remembered.

## Install as an app

On a phone, open the game link, then use Share and Add to Home Screen on iPhone, or the browser menu and Install app on Android. It launches full screen with no browser bars. The files manifest.webmanifest, icon-192.png, icon-512.png and apple-touch-icon.png must sit next to index.html.

## Emotes

Open the emote wheel by pressing Start on a controller or by clicking or tapping the smiley button at the top. Nothing else opens it. Click or tap an emote, press 1 to 6, or on a controller aim with the stick or D-pad and press A to send (B or Start closes it). Everyone sees a bubble above you, and if you are off screen it shows at the screen edge pointing your way. There is a short cooldown so nobody can spam.

## Between levels

On the Level Complete screen every player except the host gets an I am ready button and a Leave button, so someone can take a break or head out without holding up the group. The host sees a checkmark or hourglass next to each player and a Kick button on each row. Start Level shows how many players are ready. If someone is not ready the host can hold the Start button for 3 seconds to start anyway. Kicked players cannot rejoin that game.

## Invite code in game

The lobby code appears at the top of the screen during a round. Any player can tap it to copy the invite link and send it to a friend at any time. New players join as spectators and can jump in.

## Hull breach events

From Level 4 on, a hull breach can open at a random spot. After a 2 second alarm it pulls in nearby players and loose items. If a breach sucks you out, you respawn at an airlock and everything you were carrying except the 3D printer is scattered around you, drifting slowly away, so you have to collect it again. Grab a wall to resist the pull. Stay next to the hole holding 2 wrenches between you for about 3 seconds to patch it; more players patch faster, and both wrenches are used up. If nobody patches it within 30 seconds, an emergency bulkhead seals it and the self destruct timer loses 15 seconds. A player pulled into the hole is lost in space for 3 seconds, drops what they carry at their respawn point, and comes back with 40 percent fuel. Loose items pulled in reappear in the middle of the room, so nothing is ever lost.
