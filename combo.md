# Combo Skills — Optimal Power Combinations

This document provides detailed, practical combos for powers implemented in the project. Each combo entry links back to the power description in README.md for quick reference.

> Warning: Powers may be unbalanced. Test combos in Creative or a staging server before enabling them in PvP. Adjust cooldowns and limits in configuration to suit your server's balance.

## Combo Index
- [Elemental Combos](#elemental-combos)
- [Dragon & Fire Combos](#dragon--fire-combos)
- [Dark & Sustain Combos](#dark--sustain-combos)
- [Mobility & Control Combos](#mobility--control-combos)
- [Area Denial & Siege Combos](#area-denial--siege-combos)
- [Support & Battlefield Control](#support--battlefield-control)
- [Tactical Examples & Sequences](#tactical-examples--sequences)
- [Server Tuning Recommendations](#server-tuning-recommendations)

## Quick Guide
- Links point to README.md power entries (e.g. [Fire](README.md#fire)).
- "Recommended triggers" suggests typical bindings: Left Click (attack), Right Click (cast), Sneak (hold / charge), or Passive (on-move / on-hit).
- "Sequence" gives an example order to use abilities in combat.
- "Tuning" gives quick server-side config suggestions.

---

## Elemental Combos

1) Fire + Wind
- Links: [Fire](README.md#fire) + [Wind](README.md#wind)
- Role: Area damage and zone denial.
- Recommended triggers: Fire (Right Click), Wind (Right Click or Sneak+Right Click to push).
- Sequence: Wind to push enemies into burning zone → Fire to ignite and sustain damage.
- Strengths: High sustained area damage; forces enemy repositioning.
- Weaknesses: Requires line-of-sight; friendly fire risk.
- Tuning: Increase Wind cooldown or reduce Fire spread radius to avoid OP combos.

2) Ice + Lightning
- Links: [Ice](README.md#ice) + [Lightning](README.md#lightning)
- Role: Burst control + follow-up burst damage.
- Sequence: Ice to slow/freeze targets → Lightning for heavy single-target burst.
- Recommended triggers: Ice (Sneak or Left Click), Lightning (Right Click).
- Tuning: Ice duration should allow follow-up but not permanent stun.

3) Water + Earth
- Links: [Water](README.md#water) + [Earth](README.md#earth)
- Role: Crowd control and trapping.
- Sequence: Water to create slow/whirlpool → Earth to raise barriers and trap.
- Tuning: Limit barrier size or life span to prevent immortal fortresses.

## Dragon & Fire Combos

1) Phoenix / Meteor Lord + Fire
- Links: [Phoenix](README.md#phoenix) / [Meteor Lord](README.md#meteor_lord) + [Fire](README.md#fire)
- Role: High area DPS with self-healing (Phoenix) or knockdown (Meteor Lord).
- Sequence: Initiate with Meteor/Phoenix → follow with Fire aoe to maximize overlap.
- Tuning: Add cast delay to Meteor Lord to allow counterplay.

2) Ice Dragon + Snowparting Blade
- Links: [Ice Dragon](README.md#ice_dragon) + [Snowparting Blade](README.md#snowparting_blade)
- Role: Mix of close-combat and ranged freeze.
- Sequence: Use Ice Dragon ranged control then switch to Snowparting Blade for assassination.

## Dark & Sustain Combos

1) Demon / Demon Lord + Blood / Vampire
- Links: [Demon](README.md#demon) / [Demon Lord](README.md#demon_lord) + [Blood](README.md#blood) / [Vampire](README.md#vampire)
- Role: Sustain and long fights; punish prolonged engagements.
- Sequence: Engage with Demon to debuff → activate Blood/Vampire to leech health during trades.
- Tuning: Cap life-steal percentage and add stacking limit to Blood effects.

2) Curseweaver + Poison
- Links: [Curseweaver](README.md#curseweaver) + [Poison](README.md#poison)
- Role: DoT (damage over time) and debuff stacking for gradual victory.
- Sequence: Apply Curse → follow with Poison procs to stack DoT.

## Mobility & Control Combos

1) Warp + Portal (+ Superior Warp)
- Links: [Warp](README.md#warp) + [Portal](README.md#portal) + [Superior Warp](README.md#superior_warp)
- Role: Hit-and-run, repositioning, team rescue.
- Sequence: Place a Portal behind enemy lines → Warp in, hit, Warp out; Superior Warp for long escapes.
- Tuning: Add cooldown on Portal placements or limit active portals.

2) Gravity + Cloud
- Links: [Gravity](README.md#gravity) + [Cloud](README.md#cloud)
- Role: Vertical control and denial of aerial movement.
- Sequence: Cloud to gain aerial advantage → Gravity to force enemies to ground or trap them mid-air.

## Area Denial & Siege Combos

1) Meteor Lord + Shockwave + Fire
- Links: [Meteor Lord](README.md#meteor_lord) + [Shockwave](README.md#shockwave) + [Fire](README.md#fire)
- Role: Break enemy formations, clear fortifications.
- Sequence: Meteor impact → Shockwave to scatter survivors → Fire to seal the area.
- Tuning: Balance meteor frequency and shockwave knockback strength.

2) Crystal + Spike + Earth
- Links: [Crystal](README.md#crystal) + [Spike](README.md#spike) + [Earth](README.md#earth)
- Role: Build chokepoints and lethal traps.
- Sequence: Use Earth to shape ground → place Crystal barriers → lay Spike traps at chokepoints.
- Tuning: Make Spike damage conditional (triggered by enemy) to reduce accidental kills.

## Support & Battlefield Control

1) Nature + Magnetic / Crystal
- Links: [Nature](README.md#nature) + [Magnetic](README.md#magnetic) / [Crystal](README.md#crystal)
- Role: Zone control, ally support, and environmental manipulation.
- Sequence: Nature heals/roots, Magnetic repositions metal mobs/items, Crystal creates protective cover.
- Tuning: Limit range and duration of passive heals.

2) Sound + Wind
- Links: [Sound](README.md#sound) + [Wind](README.md#wind)
- Role: Disruption and CC for coordinated plays.
- Sequence: Use Sound to disorient → Wind to push enemies into unfavorable positions.

## Fun & Niche Combos
- Potato + Alcoholizm: mostly for events and minigames — avoid giving large combat bonuses.
- Unstable + Comic Test: experimental; enable only on test servers.

---

## Tactical Examples & Sequences

Example 1: 3v3 objective push (Fire/Wind + Shield)
- Setup: One player with Fire+Wind (area denial), one with Crystal+Earth (cover), one with Warp for flanking.
- Objective: Use Wind to funnel defenders into Fire zones, push the objective while shields absorb return fire.

Example 2: Boss fight sustain (Demon Lord + Vampire)
- Setup: Demon Lord to weaken boss armor, Vampire to restore health on hit.
- Objective: Rotate hits between DPS and sustain to outlast boss mechanics.

---

## Server Tuning Recommendations
- Max active powers per player: 2 or 3 recommended on PvP servers.
- Cooldown scaling: Increase cooldown for overlapping AoE combinations (Meteor+Shockwave+Fire).
- Damage caps: Use server config to cap combined damage-per-second from multiple sources to prevent instant deaths.
- Safe mode: Add a per-world or per-region toggle to disable specific powers in spawn or protected zones.

---

## Contributing new combos
- If you add or modify a power, update this file with tested combos and recommended config values.
- Please include: combo name, involved powers (links to README.md), recommended triggers, sequence, strengths/weaknesses, and tuning advice.

---

For full descriptions of each power, see README.md: [Available Powers](README.md#-available-powers)
