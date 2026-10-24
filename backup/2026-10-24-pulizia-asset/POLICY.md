# Asset store policy (catalogue artifact FXWkEdQvcnxFn6hSibBKzM)

Agreed 24 Oct 2026. Applies from now on to every agent that writes to the asset store.

1. Raw video slices. After a raw video's slices (invii-log/<id>.pezzi, invii/<id>-video) are parsed here,
   keep only the frames we use (foto, config/sala, walk index, tour, pubblico, mostra) and delete the slices,
   after a local copy and a manifest entry. Never touch slices of an upload still in progress.
2. Audio. After an audio is transcribed, keep it (invii/<id>-audio parts and config/sala-audio).
3. Exact duplicates (same sha256) collapse to one copy. Keep the copy a doc already points at; repoint any
   other doc to it first, then delete the spare copy.
4. Unreferenced frames older than one day, not used by tour, count, walk or pubblico work, are deleted after a
   local copy is taken.
5. Libraries and models (text/javascript, ASR shards) are never deleted without Patrick's OK.
6. Nothing created in the last 30 minutes, and nothing from an upload whose config/upload-corrente is active,
   is ever deleted.
7. Keep a manifest. Every deletion is listed in backup/<date>-pulizia-asset/manifest.json in the repo
   (id, sha256, type, size, created, reason) and the bytes stay in the scratchpad under cleanup/deleted/.
8. Keep at least 400 MB free in the 1 GB store before a large upload starts.
