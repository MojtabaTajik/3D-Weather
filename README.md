# 3D Weather City

A live 3D city visualization that fetches real weather data and renders it as an interactive scene. Built with [Three.js](https://threejs.org/) in a single HTML file — no build step, no dependencies beyond the CDN.

## Demo

Open `index.html` in any modern browser.

## Features

### Core
- **Live weather** — fetches current conditions from [Open-Meteo](https://open-meteo.com/) every 10 minutes, no API key required
- **15+ city skylines** — each city has hand-crafted procedural landmarks (Eiffel Tower, Big Ben, Burj Khalifa, CN Tower, Sydney Opera House, and more)
- **City switcher** — dropdown rebuilds the entire scene instantly

### Sky & Atmosphere
- **Dynamic sky gradient** — colors lerp smoothly between palettes for each weather condition
- **Sun** with glow sprite and particle halo
- **Clouds** drifting across the sky, opacity tied to cloudiness
- **Rain** particle system
- **Snow** particle system with wind drift
- **Fog** density changes with weather conditions
- **Thunder & lightning** — random point-light flashes during storms
- **Stars + Moon** — fade in with night factor; moon has a soft glow sprite
- **Shooting stars** — appear every 12–30 seconds when fully night

### Day / Night
- **Real local time** — reads each city's timezone to compute a smooth day/night factor
- **Sky darkens** to deep blue-black at night
- **Directional and ambient lights dim** at night
- **Building windows glow brighter** after dark
- **Street lamps light up** at night
- **Light pools on the road** — warm amber circles under each lamp using additive blending
- **Car headlight beams** — white light cones projected onto the road in front of each vehicle

### Street Life
- **Pedestrians** — tiny figures walking along two sidewalk lanes with a walk-bob animation
- **Umbrellas** — every pedestrian opens one when it rains, closes when skies clear
- **Cars** — two-lane traffic rolling between the sidewalks, wrapping at lane ends
- **Boats** — glide along rivers and harbours with gentle wave bobbing (water cities only)
- **Birds** — 8 birds orbiting the skyline with flapping wings
- **Crowd density by time** — rush hour (7–9am, 5–7pm local) doubles pedestrians and cars; late night nearly empties the streets

### City-Specific Details
- **Amsterdam** — De Wallen red-light district: dark canal houses with red glowing windows, pink curtains, and dark silhouettes behind the glass
- **Mexico City** — street firefight: two factions crouching behind cover, gun barrels, randomly firing muzzle flashes, and blood patches on the road

### Weather-Reactive Details
- **Snow caps on rooftops** — white caps fade onto every building during snowfall
- **Neon signs** — flickering emissive panels at night for Tokyo, NYC, Bangkok, Dubai, Seoul, Singapore, LA, and Berlin
- **Flags** — per-city positioned; wave amplitude driven by real `wind_speed_10m` from the API

### Scene Polish
- **Water ripples** — animated vertex displacement on river and canal meshes
- **Gentle camera sway** — slow sine drift for a cinematic feel

## Cities

Amsterdam, London, Paris, Berlin, New York, Los Angeles, Toronto, Tokyo, Beijing, Seoul, Bangkok, Dubai, Singapore, Mumbai, Cairo, Sydney, Moscow, Mexico City, Cape Town, Rome, Istanbul, Stockholm, Zurich, Tehran

## Tech

- [Three.js r128](https://threejs.org/) via CDN — geometry, lighting, particles, post-processing
- [Open-Meteo API](https://open-meteo.com/) — free, no key required
- Single `index.html` file, ~2600 lines, no build tooling
