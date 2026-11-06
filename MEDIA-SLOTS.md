# MEDIA SLOTS — SaveVault-DOC (prepared 2026-11-06, doc/listing prep lane)

`index.md` already embeds the final media filenames below (pattern: Intake-DOC —
cover upar → video → GIF → showcase stills, `{{ site.baseurl }}/assets/...` paths).
Nothing here is invented media: every file is produced by the capture/production
lane from real captures (set masters in `../final/`, GIF/MP4 from
`../work/assemble.sh`). Until the files land, do NOT push `index.md` — the media
commit is ONE step: copy the files into `assets/…` under these exact names, then
push `main` + `gh-pages` together and verify (curl 200 + home page shows media).

## Slots

| Target path in this tree | Source (production lane output) | Embedded in |
|---|---|---|
| `assets/images/cover-2400x1600.png` | set master `cover-2400x1600.png` (2400×1600) | index.md — hero, under the buttons |
| `assets/video/savevault-overview.mp4` | `savevault-overview.mp4` (assemble.sh video leg) | index.md — "Watch it work" |
| `assets/images/savevault-migration-beat.gif` | `savevault-migration-beat.gif` (assemble.sh GIF leg, beats 10→11→12 — the INTEGRITY beat: save written, load refused `CorruptNoBackup`, file quarantined; re-titled 2026-11-06, no migration-success claim) | index.md — "Watch it work" |
| `assets/images/showcase-04.png` | set master `showcase-08.png` — "The Wayfarer Panel" (CORRECTED 2026-11-06: build_set2 numbering differs from the original plan; the built set's showcase-04 is Storage Status, which does not belong in the Wayfarer section) | index.md — Wayfarer section |
| `assets/images/showcase-01.png` | set master `showcase-01.png` — "The Migration Centre" | index.md — Home Window section |
| `assets/images/showcase-13.png` | set master `showcase-06.png` — "Sync Lab" (CORRECTED 2026-11-06: the built set's showcase-13 is the one-window overview; Sync Lab is showcase-06. Caption on the page states review surface + Steam mock-only) | index.md — Home Window section |

## LANDED — 2026-11-06 (finisher lane)

All 6 files copied into `assets/…` under the slot names above; index.md captions
for the GIF and the Wayfarer image corrected to the integrity beat / the actual
panel image; committed and pushed to `main` + `gh-pages`; live-verified
(home 200 + all 6 asset URLs 200). The video's title card was re-titled to
"Every save, sealed. Every load, checked." before assembly (the pre-F5 card
claimed "Your players' old saves still work.").

## What waits on captures

- All 6 files above wait on Session B captures → set build (`build_set.py`) →
  `assemble.sh` (GIF + video). Session A frames are banked; Session B frames
  (panel/migration/recovery/RT) feed showcase-01/04/13 and the GIF/video beats.
- After the media commit: re-verify live — home 200 AND all 6 asset URLs 200
  (the Intake/Extraction standard), then the site may be called media-complete.
