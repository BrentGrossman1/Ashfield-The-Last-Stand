# Ashfield Last Stand

A stationary-knight horde defense game. You hold the center of a burnt field while zombies close in from every side. Kill them to earn boons, stack rare upgrades to evolve your weapon, and survive as long as you can.

Built as a standalone HTML prototype for In-Class Challenge 3.2, prototyped with AI.

**Play:** open `index.html` in a browser, or visit the GitHub Pages link for this repo.

## Controls

| Input | Action |
|---|---|
| Click / tap | Fire toward that spot (hold to keep firing) |
| 1 / 2 / 3 | Pick a boon |
| Shift + 1 / 2 / 3 | Banish that boon from the pool |
| R | Re-roll the boon cards |
| S | Show or hide the stats panel |
| P / Esc | Pause |
| M | Mute or unmute music and sound |

## How it works

- **Boons:** every few kills, pick one of three upgrades, color-coded by tier: common (grey), uncommon (green), rare (blue), epic (purple), legendary (gold). Commons have a 15% chance to roll as a blue rare at double strength, and Keen Edge can roll as a purple epic.
- **Re-rolls:** you start with 1 and earn another every 5 waves (max 3). A re-roll redraws all three cards.
- **Banishes:** 3 per run. Banishing a card removes that boon from the pool for the rest of the run and draws a replacement, without using up your pick.
- **Surges:** every 25 seconds the wave number rises. The horde scales with the wave and with how strong your build is. Through wave 10 it ramps at half speed so a run can get going, then grows at the full rate. From wave 25, zombies also get +2% movement speed per wave, up to +40%.
- **Mutations:** from wave 30, mutated zombies join the horde (8% of spawns, +1% per wave, up to 30%). They're immune to Plague Bloat, take half knockback and have 50% more health. Look for pale skin, bone spikes, glowing yellow eyes and an orange health bar.
- **Revenants:** from wave 40 (4% of spawns, +1% per wave, up to 15%). Immune to Plague Bloat and Necrotic Thrall, take a quarter of normal knockback, have 2.2x health and bite harder, but chill and freezes still work on them. Look for blackened skin with ember cracks, a bone mask, magenta eyes and a magenta health bar.
- **Sound:** all music and sound effects are synthesized in the browser with the Web Audio API, so there are no audio files. The music is a dark D-minor drone and chord loop that adds drums and speeds up as the waves climb. It starts when you press Take your post, and M mutes it (your choice is remembered).
- **Stats panel:** shows your weapon, damage, attack speed and active effects, plus the horde's current health, bite damage and arrival rate.

### Boon list

| Boon | Tier | Effect |
|---|---|---|
| Honed Broadheads | Common | +3 damage |
| Quick Draw | Common | +25% fire rate |
| Goose Fletching | Common | +25% shot speed |
| Field Dressing | Common | +20 max health, heal to full |
| Bodkin Points | Uncommon | Shots pierce one more zombie |
| Executioner | Uncommon | Direct hits kill zombies under 10% health (stacks to 25%) |
| Vampiric Tips | Uncommon | Heal 1 health per kill (stacks) |
| Overdraw | Uncommon | Every 8th shot deals triple damage (stacks down to every 4th) |
| Keen Edge | Rare / Epic | +5% crit chance, or +12% as an epic. Crits deal double damage (cap 50%) |
| Split Shot | Epic | One more projectile per shot |
| Bone-Burst Tips | Epic | Shots burst into shards on impact |
| Rime Tips | Epic | Hits chill zombies; extra Rimes add slow and a chance to freeze solid |

## Weapon evolutions

Your first 3 epics decide your first evolution:

| Your first 3 epics | First evolution |
|---|---|
| 3 Split Shot | Storm Repeater |
| 3 Bone-Burst | Hellfire Staff |
| 3 Rime | Frost Scepter |
| Split + Bone-Burst | Tempest Tome |
| Rime + Bone-Burst | Equinox Staff (fire and frost) |
| Rime + Split | No combo: whichever you took more of wins |
| One of each | Tempest Tome |

The next 3 epics decide your second evolution:

| First evolution | + 3 Split | + 3 Bone-Burst | + 3 Rime | Mixed |
|---|---|---|---|---|
| Storm Repeater | Storm Gatling | Thunder Repeater | – | Inferno Repeater |
| Hellfire Staff | Meteor Staff | Cataclysm Staff | – | Plasma Staff |
| Tempest Tome | Storm Codex | Thunderclap Tome | – | Eye of the Storm |
| Frost Scepter | Blizzard Volley | Shatter Scepter | Glacier Lance | Hailstorm |
| Equinox Staff | Solstice Staff | Solstice Staff | Solstice Staff | Solstice Staff |

On the Repeater, Staff and Tome lines, Rime Tips only adds chill and doesn't count toward the second evolution. On the Equinox Staff, fire landing on a frozen zombie causes **Thermal Shock** for triple damage; the Solstice Staff chains it to other frozen zombies.

Bone-Burst shards cap at 15 per burst. On the Tempest line they become Static Burst (forking lightning arcs) and on the Frost line they become chilling ice shards. Bone-Bursts taken after the cap add shard damage, or grow the lava pools on the Cataclysm Staff.

## Legendaries

Reaper's Harvest, Consecrated Ground (stackable, the ring grows 35% per copy), Phoenix Plume, Stormcaller, Plague Bloat, Necrotic Thrall, Grave Ward (three skulls that orbit you; each shot throws one like a boomerang that bites everything on the way out and back).

Once you own a legendary and an evolved weapon, the legendary **awakens** with an extra effect themed to your weapon line. The Equinox and Solstice staffs use the Staff line's awakenings.

| Legendary | Repeater line | Staff line | Tome line | Frost line |
|---|---|---|---|---|
| Consecrated Ground | Blessed Bolts: +1 pierce, holy trails | Holy Fire: gold flames, +50% fire damage | Radiant Smite: holy lightning, +50% damage | Hallowed Frost: the ring chills; frozen zombies burn twice as fast |
| Stormcaller | Ricochet Storm: strikes leap to a second zombie | Firestorm: strikes leave burning ground | Living Storm: strike chance doubles to 30% | Frozen Lightning: strikes freeze their blast |
| Plague Bloat | Shrapnel Bloat: bursts fire a ring of 8 bolts | Plague Fire: burning zombies can catch the plague | Infectious Arcs: lightning can infect | Frostbloat: bursts freeze what they splash |
| Necrotic Thrall | Bone Archers: thralls fire bone darts | Burning Thralls: thralls ignite what they bite | Static Thralls: thralls shock nearby zombies | Frost Thralls: thralls chill and freeze what they bite |
| Reaper's Harvest | Twin Souls: two souls per kill | Ember Souls: souls explode in fire | Chained Souls: souls chain lightning | Ice Wraiths: souls freeze what they hit |
| Phoenix Plume | Phoenix Volley: revive fires 30 piercing bolts | Ashen Rebirth: revive leaves a lava ring | Storm Rebirth: revive calls lightning for 6s | Frost Nova: revive freezes the field for 5s |
| Grave Ward | Bone Sentries: thrown skulls spit darts at the turnaround | Burning Skulls: bites ignite | Storm Skulls: bites chain lightning | Frozen Skulls: bites freeze |

