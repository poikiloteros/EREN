# EREN website — polished version

Open [index.html](index.html) in a browser (double-clicking it is fine). It is one HTML file (styles, scripts, fonts, map data and the 45 inscriptions are inside it); photographs live in [images/](images/). Everything works offline except two things loaded online: three.js for the 3D hero (jsDelivr; without it the hero shows the stone as a still image) and the optional "Roman roads" map layer.

This folder is a copy of `Claude output/` with four changes. `Claude output/` and `hero-trial/` are untouched.

## What changed from `Claude output/`

1. **Loader and riso hero** (from `hero-trial/`). A riso "drum" prints the stone sheet after sheet until the page is ready; then the sheet is pulled up and the Nicomachus Flavianus base is printed in violet and vermilion, turns to face the reader and is unmasked to the photograph. Drag the block to turn it; click it to print it again. The caption below it opens slip no. 8, as the photo slip did. The hero's entrance and the atlas strip wait for the loader to lift. The trial's control panel is gone; the block rests on the photograph, with both inks.
2. **Rooms.** Each section has its own card tone, alternating a cool violet wash and a warm paper and deepening slightly towards Contact, all far lighter than the ink colophon. The masthead takes the tone of the room under it. **Gravity:** when a scroll you made comes to rest near a room's threshold, the page finishes the move: forward into the next room if it is already about 40% in view, or back to the start of the room you just left if you only stepped out of it (up to 20%). The atlas has a second threshold, with the map framed below the masthead. Long rooms scroll freely in between. Links, search and other scrolls the page makes are never pulled, and nothing moves under reduced motion.
3. **Photographs as riso prints.** Each photograph (About, News, Conference, Prosopography, Gallery, Team) arrives covered by a light riso plate: a fine violet halftone of the image with a little vermilion in the deeper tones, out of register. Once it is well in view and loaded, a third pass of the drum unmasks it top to bottom, its ragged front riding a band of violet, as in the hero. It happens once per photograph. The plates are drawn from small tone maps the build embeds, so they also work from `file://`.
4. **Favicon.** The base, simplified to two plates: violet stone with the inscribed panel knocked out, and the vermilion panel printed one unit out of register (a paper sliver on one side, a dark overprint on the other), with three unprinted lines for the letters. SVG, a 32px PNG, and a 180px touch icon. The SVG is also saved as [images/site/favicon.svg](images/site/favicon.svg).

Also fixed: the Faculty of History logotype is now embedded, so it shows when the page is opened from Finder (browsers refuse `file://` images used as CSS masks).

Inspection, in the browser console: `ErenHero.freeze(1.2)` / `ErenHero.snap(t)` and `ErenLoader.snap(t)` (as in the trial); `ErenPlates.hold(el)` lays a fresh plate over a photograph's wrapper and leaves it, `ErenPlates.unmask(el)` lifts it; `ErenGravity.stops()` lists the room thresholds.

## What is on the page

In the order of the page: the project title and a search over the inscriptions; the **inscription atlas**; **About the project** (the original "Project info" text); **News** (the three posts of the current site, with full text); **Conference** ("Inscribed Art", with its call for papers); **Prosopography**; **Gallery** (the Aphrodisias photographs); **Team**; **Funding institutions**; **Contact**. The University of Warsaw and Faculty of History marks sit in the header and footer.

Text comes from the current EREN site with light corrections only. Every correction is listed in `EDITS` at the top of [build/data/site.py](build/data/site.py). Dr Bodnaruk is referred to as they/them throughout, as in their own bio (the project abstract on the old site said "she").

## The atlas

- Hover a place to see its inscriptions; click one to open its record ("slip") beside the map; **Lay flat** shows text and translation side by side at full screen; **Esc** or the close button files it back. Each record has a link (`#slip-08`) and a **Cite** button that copies a reference.
- The drawer on the left opens on hover (or click **Keep open**). It searches texts, translations, names, offices and places, ignoring accents and Leiden brackets. It filters by office family and specific office, form, date, language and certainty; only matching inscriptions stay on the map. Hovering an office family previews how many would remain and lights its markers.
- Marker rings show office families in four validated colours (checked for colour-blind separation): court offices and household, notaries and tribunes, finance and palatini, agentes in rebus; plus a neutral "prefects and other".
- **Places named** draws the provinces, origins and addresses that the inscriptions themselves mention (12 records), from the find place to a representative point. Solid lines are read on the stone; dashed hairlines depend on restoration. They are relationships, not routes.
- Zoom into Rome to separate its find spots (Forum Romanum, Forum of Trajan, Caelian, Quirinal, Esquiline, S. Paolo, three catacombs), drawn over the Aurelian Walls and the Tiber.

## Data corrections (details in [INSCRIPTIONS.md](INSCRIPTIONS.md))

- **Translations corrected** where the previous pilot misread the text: nos. 1, 2, 4, 7, 8, 10, 14, 20, 26, 28, 31, 39, 42 and 43. The largest: no. 43 (Tatianus) listed governor, vicar, proconsul and two prefects as his own offices; the Greek says he sat as assessor to them.
- **Missing editions recovered:** no. 22 from EDR194240 (S. Paolo fuori le mura, Lapidario Paoliano), no. 35 from EDCS-16300170 (AE 1914, 64). All 45 records now have a verified source text.
- **Working-list slips flagged on the records:** no. 2 is LSA-314 (not 344); no. 16 is CIL VI 1674; no. 24 is CIL XI 830; no. 29 names Flavius Fortunius, palatinus (not "Falatinus"); no. 36 reads Antonius Taurus; no. 37 is CIL V 304 = ILCV 1930; no. 39 can be read as the young notary (secretary) of an advocate.
- **Places:** Trismegistos IDs added for Cingulum and Sidyma; the Valley of the Kings graffiti now use Memnonia (Thebes west: Pleiades 786067, TM 1341); Rome records placed at the find spots recorded by LSA and EDR; current locations added (museum and inventory numbers where LSA/EDR give them).
- **Office families** rebuilt: quaestors and masters of memorials are court offices, not finance; centenarius and ducenarius are grades of the agentes in rebus.
- **Images:** archival drawings and photographs for nos. 1 (related object), 2, 3, 6, 9, 19, 20 and 27 added to the existing 8 and 28; place photographs for Rome, Cuicul, Simitthus, Sidyma, Tolentinum and the Valley of the Kings (KV9 graffiti, photographed by the Polish Centre of Mediterranean Archaeology, University of Warsaw). Credits on every record and in [images/README.md](images/README.md).

## Please check

1. **EU disclaimer.** The funding section uses the standard MSCA wording naming the European Research Executive Agency (REA). The conference call for papers names the ERC Executive Agency instead; confirm which the project should use.
2. **PLRE references.** Numbers are given only where verified (Stilicho; Flavianus 15; Secundus 3; Saturninus 9; Theodorus 27; Tatianus 5). The rest read "s.v." and need the volume checked.
3. **Translations** remain provisional working renderings for review.
4. **Image terms.** Photographs from the current EREN site (news, gallery, team, project) and the portrait are reused as on that site; confirm before wider publication.

## Rebuilding

```
python3 build/prepare_hero.py   # only when images_edits/hero base.png changes
python3 build/build.py
```

`build.py` needs Pillow and NumPy (tone maps for the photographs' plates, favicons). Inputs: `build/data/` (records and translations in `records.py`, site copy in `site.py`, places in `places.json`, source snapshots, and `hero-assets.js` written by `prepare_hero.py`), `build/src/` (template, styles, `app.js`, and the hero's `loader.js` and `hero.js`) and `build/vendor/` (Leaflet 1.9.4, fonts, Natural Earth and OpenStreetMap extracts). Outputs: `index.html`, `INSCRIPTIONS.md`, `images/README.md`, `images/site/favicon.svg`.

## Design

Two inks on card — registry violet and card white — with one vermilion rule taken from the Faculty of History logotype's orange. The page borrows the grammar of a prosopographer's slip file: ruled lines under the title and the texts, a red head rule on every card, coloured signal tabs for office families, stamps for doubt. Type: Brygada 1918 (a Polish revival face) for headings and reading, Cardo for the Latin and Greek texts, Archivo for labels and controls; all SIL Open Font License, embedded.

Licences: three.js (MIT); Leaflet (BSD-2-Clause); Natural Earth (public domain); Rome walls and Tiber © OpenStreetMap contributors (ODbL); DARE tiles (J. Åhlfeldt, CC BY 4.0); EDR epigraphic data CC BY-NC-SA 4.0.
