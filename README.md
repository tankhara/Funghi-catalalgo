# Funghi in mostra

A phone-first catalog for a mushroom exhibition (mostra micologica). It records which species are on display and which zone (zona) and spot (posto) each one sits in, ordered systematically.

- **Registra**: work spot by spot. Tap the zone on the room plan, pick the spot, dictate the species with the phone keyboard's microphone, take a photo and save, then the page moves to the next spot. If every name is recognised with certainty it saves straight away, with an undo. If a name is uncertain, or a species is already somewhere else (a move), you get a list to confirm. Claude can also suggest species from the photo.
- **Registra · Tratto intero**: a video filmed while walking along a zone, or a few photos in sequence. The page pulls frames out of the video in the browser, Claude splits them into plates in visitor-path order and assigns consecutive spots, and the frames become the zone's photo strip on the map, with the names placed on the photos. The species dictated in order act as a strong hint.
- **Detta**: an on-page dictation button (Web Speech, it-IT). It first asks the browser for the microphone, which shows Chrome's permission prompt, then listens. If it still can't listen, it says why, with the error code.
- **Cerca**: "where is it / do we have it already?". Results show the zone, spot and photo. A voice command such as "sposta Russula virescens in zona 4 posto 2" moves a species. "corsia", "sezione" and "tavolo" work as synonyms of "zona", as do the short names ("all'angolo polipori", "alla parete", "in U fondo").
- **Mappa**: a plan of the room, and each zone spot by spot with its photo and species.
- **Catalogo**: every species grouped by sector and family, with CSV export.
- **Schema**: the systematic display order, which suggests where new species should go, and the zone names.

## Room zones

Zones are numbered in the order a visitor walks them. Spot 1 is where each zone starts in that direction.

| Zone | Where | Default sectors |
|---|---|---|
| Zona 1 · U sinistra | Left arm of the central U, from the entrance to the back | Hygrophoraceae, Tricholomataceae, Entolomataceae |
| Zona 2 · Polipori | Back-left corner by the window | Polypores and other wood-rotting fungi |
| Zona 3 · U fondo | The bend of the U at the back, left to right | Amanitaceae, Lepiotaceae and Agaricaceae, Pluteaceae, Strophariaceae, Coprinaceae and Bolbitiaceae, Cortinariaceae |
| Zona 4 · U destra | Right arm of the U, from the back towards the exit | Paxillaceae and Gomphidiaceae, Boletaceae, Russulaceae |
| Zona 5 · Parete | About 3 m on the right wall, before the door | Chanterelles, hedgehogs and corals, gasteromycetes, jelly fungi, Ascomycota, others |

One door at the front serves as both entrance and exit, with the souvenir stand next to it. A table of logs before the window corner is decoration only and holds no species.

The display order follows, for now, the classic order of the traditional field guides: Hygrophoraceae and Tricholomataceae first, then Entolomataceae, Amanitaceae, Agaricaceae, Pluteaceae and the coloured-spored families, then Boletaceae and Russulaceae, the Aphyllophorales, gasteromycetes (puffballs included), jelly fungi and Ascomycota. The sector assignment is provisional until the official ordering scheme is in. Names and assignments can be changed in Schema.

Dictated names are matched against a reference list of about 830 species, including synonyms and the phonetic distortions of Italian speech recognition (e.g. "chanoxanta" becomes *cyanoxantha*). Names that don't match with certainty go to Claude.

`index.html` is a self-contained page published as a claude.ai Artifact. It uses the artifact database (`specie`, `foto` and `config/layout` collections), the asset store for photos, and Claude for recognition. Opened anywhere else, it falls back to browser storage without photos.

## Later: mostra virtuale

A planned public site built from the same data: the species list, the photos of each spot, the stretch videos and the room plan, so people can walk the exhibition online. Things to keep in mind while collecting, so the material is usable later:

- one clean, well-lit photo per species, alongside the spot photos;
- the stretch videos, filmed slowly in the visitor direction;
- notes meant for the public kept apart from working notes;
- possibly a short description per species and the collector or place found, if wanted.

Nothing private (working notes, the editing tools) would be exposed. The public site would read an exported copy, not the working database.
