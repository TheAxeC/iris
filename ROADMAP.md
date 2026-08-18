# Features

## World

- 96 by 96 continent generated from a seed
- six levels of elevation, terraced, with cliff faces between them
- water, sand, grass and rock, all derived from height
- coastline from an island falloff, and open sea drawn past the map border
- contour jitter so terrace edges wander instead of following smooth lines
- guaranteed to be a single connected landmass; anything unreachable is drowned
- seeds that fragment into islets are rejected and rerolled
- ambient occlusion baked once per map

## Terrain art

- every tile image drawn at startup from code, nothing loaded
- four levels of vitality per terrain type, three variants of each
- grass grows taller and puts out flowers in the owning herd's colour
- water clears and brightens as it comes back to life
- rock gets angular chips, sand gets highlights, everything gets mottling

## Units

- three types: foal, charger, prism
- eight facings and a four frame walk cycle for each
- every sprite comes from one 3D description per type, rotated and projected
- dark silhouette pass, drop shadows, health bars and hit flashes
- four herd colours, each with its own coat, mane, horn and barding

## Movement

- flow field pathfinding, one search per destination, shared by every unit going there
- steps may climb or drop one terrace, never more
- no cutting corners diagonally around a cliff
- water and buildings block
- separation steering so a herd spreads out instead of stacking
- units eased between terrace heights rather than snapping

## Buildings

- grove, stable and spire, each on a flat two by two of living ground you own
- each trains its own unit type on a timer
- each raises the population you can support
- each costs half again as much as the last of its kind
- groves and spires bring ground back to life around themselves
- placement highlights every legal tile while a building is armed
- units standing where a building goes are pushed clear

## Economy

- one resource, bloom, earned from every living tile you hold
- units are trained free; bloom only buys buildings
- population capped by your buildings and by a limit set in the lobby
- ground that has been brought back stays back; only a rival can take it away

## Combat

- rock paper scissors between the three unit types
- prisms outrange everything and fire visible beams
- attacking from higher ground does more damage
- units notice hostiles nearby and engage on their own
- anything that takes a hit turns on whoever hit it
- move orders override combat until the unit arrives
- buildings can be attacked from any side, and targeted directly by clicking them
- bodies bleach the ground where they fall

## Rivals

- one to three, each in its own colour
- they use the same prices, rules, placement checks and pathfinding as the player
- they expand along their frontier, build, mass a wave, then commit it at the nearest rival grove
- three difficulty settings, changing how often they decide, how large a wave they gather, how much they bank before building, and how much of the herd they send out
- difficulty never changes their income or prices

## Audio

- every sound synthesised at runtime, no samples
- effects for melee, prism beams, deaths, buildings placed and razed, selection
- music built from the board, one voice per herd at a volume set by the ground it holds
- a herd being pushed off the map fades out of the chord
- mute, and a cap on how many sounds can start at once

## Interface

- lobby for opponents, herd size, game speed, rival difficulty and victory conditions
- new world rerolls the continent while you watch
- territory bar showing every herd's share against the blight
- build panel with costs, and a hint line that changes with what you have not done yet
- pause, restart, and a result screen
- camera pan, cursor-anchored zoom, box selection

## Victory

- dominion, by holding a share of the continent that scales with the number of herds
- conquest, by destroying every rival grove
- either can be switched off, and the rivals can reach both

## Not in yet

- minimap
- entering a seed by hand
- attack-move as a separate order
- rivals retreating from a losing fight
- audio pausing when the tab loses focus
