# Funghi in mostra

A phone-first catalog for a mushroom exhibition (mostra micologica). It records which species are on display and which lane (corsia) each one sits in, ordered systematically.

- **Aggiungi**: type or dictate a name, using the phone keyboard's microphone. Fuzzy matching handles misheard Latin, and the reference list covers about 270 Italian species with their synonyms. The page shows right away whether a species is already on display and where. Names it can't match are sent to Claude for recognition. In the "Elenco dettato" mode you can dictate a whole lane in one go.
- **Catalogo**: every species grouped by sector and family, with CSV export.
- **Corsie**: a plan of the room and each lane's species in placement order.
- **Schema**: the display order (systematic by order and family, with Agaricales split by spore colour) and which lane each sector goes in.

`index.html` is a self-contained page published as a claude.ai Artifact. There it stores data in the artifact database and uses Claude for name recognition. Opened anywhere else, it falls back to browser storage.
