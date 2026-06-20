# VISION — AI-leerlog loop

## Doel
Elke ochtend automatisch één bondige, direct toepasbare AI-dagles produceren voor
Thomas (Groeimaten), op basis van de nieuwste video's van 5 vaste AI-kanalen.
Eén keer gebouwd, daarna autonoom draaiend — geen handmatig prompts tikken.

## Wat de output bevat
Eén dagles `lessen/les_[DATUM].md` met exact deze secties:
- 🚨 KRITIEK — nu uitvoeren (alleen écht waardevolle acties; leeg mag)
- 💡 Belangrijkste lessen (per video 2-5 bullets + bron-URL)
- 🔧 Concreet toepasbaar bij Groeimaten (vertaling naar agents/skills/klantwerk)
- 📌 Goed om te weten (nieuwsupdates, één regel per item)
- 🔗 Bronnen (titel + URL)

Plus `input/input_[DATUM].md` met de geselecteerde video's + ruwe notities.

## Wanneer is het "klaar" (done-criteria)
Een run is geslaagd wanneer ALLE onderstaande punten kloppen:
1. RSS van alle 5 kanalen opgehaald; selectie gemaakt (48u, anders 7d-fallback).
2. Beide bestanden bestaan voor de datum van vandaag, in de juiste structuur.
3. Elke verwerkte video heeft minstens één geverifieerde bron-URL.
4. Commit + push naar `thomasgroeimaten/ai-leerlog` is geslaagd.
5. Slotmelding gegeven: aantal video's, kanalen, paden.

Geen nieuwe video's in 7 dagen? Dan is "klaar" = korte notitie gepusht
("Geen nieuwe AI-video's deze week — geen leerlog") en stoppen.

## Wat het NIET is
Geen hype/reclame overschrijven, geen dubbele lessen (check of een video gisteren
al verwerkt is), geen forceren van KRITIEK-items als er niets kritieks is.

## Trigger
Dagelijks 06:20, na de KICK OFF-routine.
