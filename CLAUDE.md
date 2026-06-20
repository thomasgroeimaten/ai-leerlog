# AI LEERLOG — Agent Instructies

Dagelijkse AI-lesroutine voor Thomas Ghobadi (Groeimaten).
Draait elke ochtend om 06:20, na de KICK OFF-routine.

---

## STAP 1 — Haal recente video's op via YouTube RSS

Fetch de RSS feeds van alle 5 kanalen:

- https://www.youtube.com/feeds/videos.xml?channel_id=UC2ojq-nuP8ceeHqiroeKhBA (Nate Herk)
- https://www.youtube.com/feeds/videos.xml?channel_id=UCPR4DV8qMQVs_YBa-CQZQBQ (Jake Van Clief)
- https://www.youtube.com/feeds/videos.xml?channel_id=UChpleBmo18P08aKCIgti38g (Matt Wolfe)
- https://www.youtube.com/feeds/videos.xml?channel_id=UCMwVTLZIRRUyyVrkjDpn4pA (Cole Medin)
- https://www.youtube.com/feeds/videos.xml?channel_id=UC_x36zCEGilGpB1m-V4gmjg (IndyDevDan)

Selecteer video's gepubliceerd in de afgelopen 48 uur. Als er geen video's zijn van de laatste 48 uur, neem dan de meest recente video per kanaal van de laatste 7 dagen.

Zijn er helemaal geen nieuwe video's in de afgelopen week? Stop dan met de melding: "Geen nieuwe AI-video's deze week — geen leerlog." Commit en push een korte notitie naar GitHub.

---

## STAP 2 — Zoek video-inhoud op

Voor elke geselecteerde video: zoek via WebSearch naar samenvattingen, artikelen, LinkedIn-posts of andere bronnen die de kernpunten beschrijven. Gebruik de video-titel + kanaalnaam als zoekterm. Filter hype/reclame weg. Focus op concreet toepasbare technieken, met voorrang voor Claude / Claude Code / Anthropic / agents boven generieke tools.

---

## STAP 3 — Schrijf de dagles

Maak de dagles in exact deze structuur (Nederlands, bondig, in Thomas' agency-context):

```
# AI-leerlog — [datum]

## 🚨 KRITIEK — nu uitvoeren
(ALLEEN écht waardevolle, concrete acties die Thomas/Groeimaten direct moet doorvoeren.
Per item: WAT, WAAROM, en de concrete eerste stap.
Twijfel je of iets kritiek is? Dan hoort het bij 'Belangrijkste lessen', niet hier.
Leeg laten mag — niet forceren.)

## 💡 Belangrijkste lessen (vooral Claude)
(Per video 2-5 bullets met de kern. Vermeld per blok de bron-video + URL.)

## 🔧 Concreet toepasbaar bij Groeimaten
(Hoe vertaalt dit naar Thomas' setup: agents, skills, klantwerk,
automatisering, keukens/badkamers-niche.)

## 📌 Goed om te weten (nieuws/updates)
(Korte AI-nieuwsupdates — releases, tools, trends. Eén regel per item.)

## 🔗 Bronnen
(Lijst van video's: titel + URL.)
```

**Modelvoorkeur Thomas: claude-opus-4-8** (geen Sonnet).

---

## STAP 4 — Sla op

### 4a. GitHub (altijd — ook vanuit remote sessie)

Schrijf twee bestanden en commit+push naar GitHub (`thomasgroeimaten/ai-leerlog`):

- `input/input_[DATUM].md` — lijst van geselecteerde video's + ruwe notities
- `lessen/les_[DATUM].md` — de volledige dagles

```bash
cd /home/user/ai-leerlog
git add input/input_[DATUM].md lessen/les_[DATUM].md
git commit -m "leerlog [DATUM]: [aantal] video's verwerkt"
git push -u origin main
```

Bij push-fout door netwerk: retry tot 4x met 2s/4s/8s/16s backoff.

### 4b. Lokaal op Thomas' pc (alleen wanneer lokaal gedraaid vanuit VS Code)

Sla de les OOK op als:

```
C:\2. BEDRIJF\AI-leerlog\les_[DATUM].md
```

Maak de map aan als die nog niet bestaat:

```
C:\2. BEDRIJF\AI-leerlog\
```

Controleer eerst of het pad bereikbaar is. Draait de agent in een remote/cloud-omgeving zonder toegang tot C:\? Sla deze stap dan stil over — geen foutmelding, gewoon doorgaan.

---

## STAP 5 — Klaar

Meld kort:
- Hoeveel video's verwerkt
- Welke kanalen
- Pad naar de les (GitHub + eventueel lokaal)
