# Project Fail Mary

A zero gravity co-op and competitive ship repair game that runs in the browser. Float around a broken spaceship as a five legged crawler, grab walls, push off, repair the panels, then race your friends to finish the final reactor repair before the ship self destructs.

Play it: https://justinoros.github.io/project-fail-mary/

No install, no server, no account. It is a single `index.html` file.

## Playing with friends

1. One player opens the page, sets a name and color, and clicks **Create Lobby**.
2. Click the clipboard button to copy an invite link and send it to friends.
3. Friends click the link, pick a name and color, and click **Join**. Each friend taps **I am ready** in the lobby, and the host sees a checkmark next to everyone who is loaded and ready. The host can still start early by pressing Start twice. They can also open the page, type the 4 letter code, and click **Join Lobby**.
4. The host clicks **Start**.

You can also click **Play Solo** to try the game alone.

Multiplayer uses free peer to peer connections (PeerJS). If someone cannot join, a strict network or firewall may be blocking direct connections. Try a different network or a phone hotspot.

## How a round works

- Repair every red panel in the ship. Panels repair faster the more players work on them together.
- Whoever finishes a panel takes its tool, shown as a wrench next to their name and in their inventory.
- Once all panels are fixed, the reactor unlocks. The final repair only progresses while every tool is inside the reactor ring, whether a player is carrying it or it is lying on the floor there, no matter who is doing the repair. The first player to finish the final repair wins the round and gets the most points.
- A self destruct timer is running. If time runs out, the ship explodes and everyone loses.
- After each round a scoreboard shows everyone's points until the host starts the next level.
- There are 10 levels, and each one is bigger and nastier than the last.

## Scoring

| Action | Points |
| --- | --- |
| Finish the final repair | 300 |
| Finish a panel | 60 |
| Help repair a panel | 40 |
| Collect a star | 20 |

## Moving around

You float in zero gravity, so momentum is everything.

- Hold **grab** next to a wall to stick to it. Fly into a friend while holding grab and you cling to them and ride along as they move. Release to push off them. You cannot grab someone who is already riding another player.
- Release grab to push off toward where you are aiming. Holding grab longer before releasing gives a harder push.
- Thrusters give you extra control, but fuel is limited and does not refill on its own.
- Hold **repair** inside the dashed ring around a panel to work on it. Letting go, drifting out of the ring, or getting stunned resets the progress back to zero.
- Fuel boxes refill half a tank. Just fly into one. A box is ignored while your tank is almost full, so it stays for someone who needs it.
- You can share your own fuel with a nearby friend by holding **share fuel** next to them.
- Crawlers bump into each other, so you can knock a friend off a panel.

## Inventory and tools

- The row of slots at the bottom of the screen is your inventory. New items, including tools, go into the first free slot.
- Select a slot with the number keys 1 to 9, the mouse wheel, a click, or left and right on the D-pad. The selected item is equipped and shown in your crawler's hand.
- Drop the selected item with Q, right click on a slot, or X on a controller. Dropped items float away, and anyone can pick them up by touching them. You cannot pick your own drop back up for about a second and a half.
- Tools are heavy. Every tool you carry makes your thrusters weaker, lowers your top speed, weakens your push off, and burns fuel faster. Dropping tools at the reactor ring is a good way to ferry them.
- More item types will be added later.

## Colored doors and keys

From level 2 on, some doorways between rooms are sealed with a colored lock. A key of the same color is lying somewhere in the ship, always in a part you can reach before that door.

- Pick up a key by touching it. It goes into your inventory and has no weight.
- Carry the key and touch the matching door to unlock it for everyone. The key is used up.
- Keys can be dropped and passed to friends like any other item.
- Locked doors are shown on the minimap in their color.

## The Blip-A

The ship you are repairing is the Blip-A, and it is slowly rotating clockwise. Outside, a red planet, a tethered research spacecraft and a spacewalking astronaut drift past the hull in the other direction, so you can always tell the ship is spinning.

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
| Thrusters | Shift or right click | RT, RB or B |
| Repair and capture | E or F | Y |
| Share fuel | G | LT |
| Select inventory slot | 1 to 9 or mouse wheel | D-pad left and right |
| Drop item | Q or right click a slot | X |
| Chat | Enter | Select or View |
| Mute | M | |

Click the cog at the top of the screen to rebind any keyboard key.

In menus on a controller, use the D-pad or stick to move, A to select, B to go back, and Start to confirm. Selecting the name or code box opens a built in on screen keyboard.

## Phones and tablets

Touch controls appear automatically on a touchscreen. Landscape gives the widest view, and the game adjusts when you rotate your phone.

- Drag anywhere on the left side of the screen to aim. Release to keep your last heading.
- The buttons on the right copy an Xbox controller: A grabs, B thrusts, Y repairs and X drops the selected item. LT shares fuel. Hold them like the keyboard keys.
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

A low engine hum plays while you are aboard the Blip-A, and a tense pulsing bass line speeds up and gets louder as the self destruct timer runs down. Mute with your mute key.

## Install as an app

On a phone, open the game link, then use Share and Add to Home Screen on iPhone, or the browser menu and Install app on Android. It launches full screen with no browser bars. The files manifest.webmanifest, icon-192.png, icon-512.png and apple-touch-icon.png must sit next to index.html.

## Co-op panels

From Level 3 on, some repair panels show a number badge. That is how many players must repair the panel at the same time. Levels 1 and 2 never need more than one player. The number never goes above the players actually in the round, so a small crew or a solo player can always finish. If anyone lets go, the repair resets.

## Emotes

Open the emote wheel by pressing Start on a controller or by clicking or tapping the smiley button at the top. Nothing else opens it. Click or tap an emote, press 1 to 6, or on a controller aim with the stick or D-pad and press A to send (B or Start closes it). Everyone sees a bubble above you, and if you are off screen it shows at the screen edge pointing your way. There is a short cooldown so nobody can spam.

## Between levels

On the Level Complete screen every player except the host gets an I am ready button and a Leave button, so someone can take a break or head out without holding up the group. The host sees a checkmark or hourglass next to each player and a Kick button on each row. Start Level shows how many players are ready. If someone is not ready the host can hold the Start button for 3 seconds to start anyway. Kicked players cannot rejoin that game.

## Invite code in game

The lobby code appears at the top of the screen during a round. Any player can tap it to copy the invite link and send it to a friend at any time. New players join as spectators and can jump in.

## Hull breach events

From Level 4 on, a hull breach can open at a random spot. After a 2 second alarm it pulls in nearby players and loose items. Grab a wall to resist the pull. Carry a repair tool (keys do not count) to the hole and hold the repair key for about 3 seconds to patch it; more players patch faster, and the tool is not used up. If nobody patches it within 30 seconds, an emergency bulkhead seals it and the self destruct timer loses 15 seconds. A player pulled into the hole is lost in space for 3 seconds, drops what they carry at their respawn point, and comes back with 40 percent fuel. Loose items pulled in reappear in the middle of the room, so nothing is ever lost.
