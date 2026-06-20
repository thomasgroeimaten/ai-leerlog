# CLAUDE — operationele regels per iteratie (AI-leerlog loop)

Dit zijn de vaste regels die élke run volgt. De gedetailleerde stappen staan in
`PROMPT.md`; de losse begrenzingen onderaan zijn hard.

## Model
- **claude-opus-4-8** (geen Sonnet). Vaste voorkeur Thomas.

## Stijl & format
- Nederlands, bondig, in Thomas' agency-context (keukens/badkamers-niche).
- Exacte sectiestructuur uit `VISION.md` aanhouden — niet afwijken.
- Voorrang voor Claude / Claude Code / Anthropic / agents boven generieke tools.
- Filter hype en reclame weg; alleen concreet toepasbare techniek.
- KRITIEK-sectie: alleen écht waardevolle directe acties. Twijfel? → "Belangrijkste
  lessen". Leeg laten mag — niet forceren.

## Selectieregels
- Video's uit de afgelopen 48u. Geen enkele? → meest recente per kanaal uit 7d.
- Helemaal niets in 7 dagen? → korte notitie pushen en stoppen.
- Verwerk een video NIET opnieuw als die in de les van gisteren al stond.

## Opslag
- Altijd: `input/input_[DATUM].md` + `lessen/les_[DATUM].md`, commit + push.
- Lokaal (alleen bij lokale run met toegang tot C:\): kopie naar
  `C:\2. BEDRIJF\AI-leerlog\les_[DATUM].md`. Remote zonder C:\? → stil overslaan.

## Fout = les (institutioneel geheugen)
Elke herhaalde fout die hier gecorrigeerd wordt, wordt hieronder vastgelegd zodat
elke volgende run beter is dan de vorige. Voeg correcties toe onder "Geleerde fouten".

### Geleerde fouten
- (nog leeg — vul aan zodra een run iets fout doet)

---

## 🛑 Drie harde begrenzingen (verplicht)
1. **Max iteraties:** stop na maximaal **20** interne herschrijf-/correctiepogingen
   binnen één run. Niet klaar? → push wat er is met status "INCOMPLEET" + reden.
2. **No-progress detectie:** bij **2× dezelfde fout achter elkaar** (identieke
   foutmelding of vastlopende stap) → direct stoppen, niet blijven herproberen.
   Push-netwerkfout is de uitzondering: retry 4× met 2/4/8/16s backoff.
3. **Tokenbudget:** plafond van **~150k tokens** per run. Bij overschrijding →
   afronden met wat er is en stoppen; niet doorgaan op halve context.
