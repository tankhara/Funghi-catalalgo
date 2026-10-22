# Funghi in mostra

A phone-first catalog for a mushroom exhibition (mostra micologica). It records which species are on display and which lane (corsia) each one sits in, ordered systematically.

- **Registra**: work spot by spot. Pick the lane and spot, dictate the species with the phone keyboard's microphone, take a photo and save, then the page moves to the next spot. If every name is recognised with certainty it saves straight away, with an undo. If a name is uncertain, or a species is already somewhere else (a move), you get a list to confirm. Claude can also suggest species from the photo.
- **Registra · Tratto intero**: a video filmed while walking along a lane, or a few photos in sequence. The page pulls frames out of the video in the browser, Claude splits them into plates in visitor-path order and assigns consecutive spots, and the frames become the lane's photo strip on the map, with the names placed on the photos. The species dictated in order act as a strong hint.
- **Detta**: an on-page dictation button (Web Speech, it-IT). If the page doesn't allow the microphone, the button disappears and you use the keyboard mic.
- **Cerca**: "where is it / do we have it already?". Results show the lane, spot and photo. A voice command such as "sposta Russula virescens in corsia 2 posto 4" moves a species.
- **Mappa**: a plan of the room, and each lane spot by spot with its photo and species.
- **Catalogo**: every species grouped by sector and family, with CSV export.
- **Schema**: the systematic display order, which suggests where new species should go, and the lane names.

Dictated names are matched against a reference list of about 830 species, including synonyms and the phonetic distortions of Italian speech recognition (e.g. "chanoxanta" becomes *cyanoxantha*). Names that don't match with certainty go to Claude.

`index.html` is a self-contained page published as a claude.ai Artifact. It uses the artifact database (`specie`, `foto` and `config/layout` collections), the asset store for photos, and Claude for recognition. Opened anywhere else, it falls back to browser storage without photos.
