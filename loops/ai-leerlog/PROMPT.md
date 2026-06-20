# PROMPT — kernopdracht AI-leerlog loop

Voer de dagelijkse AI-leerlog uit volgens `VISION.md` (doel + klaar-criteria) en
`CLAUDE.md` (regels + begrenzingen). Werk autonoom; stop wanneer alle done-criteria
uit VISION zijn afgevinkt of een harde begrenzing ingrijpt.

## Iteratie-patroon
prompt → output lezen → klaar volgens VISION? → zo nee: corrigeer en herhaal → zo ja: stop.

## Stappen

**1 — Haal recente video's op (YouTube RSS)**
Fetch deze 5 feeds, selecteer volgens de selectieregels in CLAUDE.md (48u → 7d-fallback):
- Nate Herk     — https://www.youtube.com/feeds/videos.xml?channel_id=UC2ojq-nuP8ceeHqiroeKhBA
- Jake Van Clief — https://www.youtube.com/feeds/videos.xml?channel_id=UCPR4DV8qMQVs_YBa-CQZQBQ
- Matt Wolfe    — https://www.youtube.com/feeds/videos.xml?channel_id=UChpleBmo18P08aKCIgti38g
- Cole Medin    — https://www.youtube.com/feeds/videos.xml?channel_id=UCMwVTLZIRRUyyVrkjDpn4pA
- IndyDevDan    — https://www.youtube.com/feeds/videos.xml?channel_id=UC_x36zCEGilGpB1m-V4gmjg

**2 — Zoek video-inhoud op (WebSearch)**
Per video: zoek samenvattingen/artikelen/posts met titel + kanaalnaam als zoekterm.
Minstens één geverifieerde bron-URL per video (done-criterium 3).

**3 — Schrijf de dagles**
Maak `lessen/les_[DATUM].md` in de exacte structuur uit VISION.md.
Maak `input/input_[DATUM].md` met de geselecteerde video's + ruwe notities.

**4 — Sla op + push**
```bash
cd <repo-root>
git add input/input_[DATUM].md lessen/les_[DATUM].md
git commit -m "leerlog [DATUM]: [aantal] video's verwerkt"
git push -u origin main   # bij netwerkfout: retry 4x, backoff 2/4/8/16s
```
Lokale kopie alleen bij lokale run (zie CLAUDE.md).

**5 — Klaar**
Meld kort: aantal video's, welke kanalen, paden (GitHub + evt. lokaal).

## Stop-condities
- Alle done-criteria uit VISION afgevinkt → klaar.
- Geen nieuwe video's in 7 dagen → notitie pushen + stoppen.
- Harde begrenzing uit CLAUDE.md geraakt → afronden + stoppen.
