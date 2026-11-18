# Project Fail Mary

A zero gravity co-op and competitive ship repair game that runs in the browser. Float around a broken spaceship as a five legged crawler, grab walls, push off, repair the panels, then race your friends to finish the final reactor repair before the ship self destructs.

Play it: https://justinoros.github.io/project-fail-mary/

No install, no server, no account. It is a single `index.html` file.

## Playing with friends

1. One player opens the page, sets a name and color, and clicks **Create Lobby**.
2. Copy the 4 letter code with the clipboard button and send it to friends.
3. Friends open the same page, enter the code, and click **Join Lobby**.
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

- Hold **grab** next to a wall to stick to it.
- Release grab to push off toward where you are aiming. Holding grab longer before releasing gives a harder push.
- Thrusters give you extra control, but fuel is limited and does not refill on its own.
- Hold **repair** inside the dashed ring around a panel to work on it. Letting go, drifting out of the ring, or getting stunned resets the progress back to zero.
- Fuel boxes work the same way: hold repair inside their ring to capture one for half a tank.
- You can share your own fuel with a nearby friend by holding **share fuel** next to them.
- Crawlers bump into each other, so you can knock a friend off a panel.

## Inventory and tools

- The row of slots at the bottom of the screen is your inventory. New items, including tools, go into the first free slot.
- Select a slot with the number keys 1 to 9, the mouse wheel, a click, or left and right on the D-pad. The selected item is equipped and shown in your crawler's hand.
- Drop the selected item with Q, right click on a slot, or Y on a controller. Dropped items float away, and anyone can pick them up by touching them. You cannot pick your own drop back up for about a second and a half.
- Tools are heavy. Every tool you carry makes your thrusters weaker, lowers your top speed, weakens your push off, and burns fuel faster. Dropping tools at the reactor ring is a good way to ferry them.
- More item types will be added later.

## Hazards

Hazards ramp up as levels go on: electric orbs, steam vents, slick walls you cannot grab, debris storms, black holes that suck you out and respawn you, and lights out darkness.

## Controls

| Action | Keyboard and mouse | Controller |
| --- | --- | --- |
| Aim | Mouse, WASD or arrow keys | Left stick |
| Grab and push off | Space or left click | A or LB |
| Thrusters | Shift or right click | RT, RB or B |
| Repair and capture | E or F | X |
| Share fuel | G | LT |
| Select inventory slot | 1 to 9 or mouse wheel | D-pad left and right |
| Drop item | Q or right click a slot | Y |
| Chat | Enter | Select or View |
| Mute | M | |

Click the cog at the top of the screen to rebind any keyboard key.

In menus on a controller, use the D-pad or stick to move, A to select, B to go back, and Start to confirm. Selecting the name or code box opens a built in on screen keyboard.

## Chat

Press Enter in a lobby or during a game to type a message to everyone. On a controller, press Select or View to open the on screen keyboard, which includes a few emoji keys.

## Browser support

Works in current Chrome, Edge, Firefox and Safari. Xbox Edge works with a controller. The PlayStation browser may be unreliable.

## Hosting your own copy

The whole game is `index.html`. Put it in any static host, such as GitHub Pages, and it works. It must be served over HTTPS for multiplayer to connect.
