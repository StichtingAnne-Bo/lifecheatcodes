> Een interactief kennisplatform vol praktische "how to do life"-artikelen voor de meiden van **Stichting Anne-Bo** — van je eerste stagedag tot slim koken op een studentenbudget.

**Korte omschrijving (voor het GitHub About-veld):**
Interactief platform met praktische levensvaardigheden voor jonge studenten: werk & stage, geld, kleding, koken en mentale gezondheid. Gemaakt voor Stichting Anne-Bo.

---

## Over het project

Studeren is meer dan tentamens halen. Het is ook: een mail sturen naar je stagebegeleider, je toeslagen aanvragen, weten wat je aantrekt naar een sollicitatie en gezond eten van weinig geld. Voor veel meiden is er niemand die dit soort dingen uitlegt.

**Life Cheat Codes** verzamelt die praktische kennis op één plek: korte, concrete artikelen met echte tips, scripts en checklists — warm en gelijkwaardig geschreven, nooit betuttelend. Zo kunnen de studenten en coaches van Anne-Bo alles teruglezen wat ze nodig hebben om zelfstandig hun weg te vinden.

Het platform is een interactieve pagina, opgebouwd met HTML/CSS/JS, waarin de artikelen per rubriek te doorzoeken en te lezen zijn.

## Voor wie

- **Studenten** van Stichting Anne-Bo — meiden voor wie studeren anders niet vanzelfsprekend zou zijn.
- **Coaches** die hen begeleiden en naar concrete uitleg willen kunnen verwijzen.
- Iedereen die praktische, betaalbare levenshulp zoekt.

## Rubrieken

| Rubriek | Waar het over gaat |
|---|---|
| **Werk & Stage** | Je eerste stagedag, netwerken, feedback en alles eromheen. |
| **Money Matters** | Bruto/netto, belasting, sparen en je eerste salarisgesprek. |
| **Dress to Impress** | Wat trek je aan? Per sector, per seizoen — en waar je het betaalbaar koopt. |
| **Personal Branding** | LinkedIn, je profielfoto, AI en hoe je online overkomt. |
| **Girl Dinners** | Lekker eten op een studentenbudget. Met meal prep en recepten. |
| **Zelfstandig wonen** | Huur, energie, de gemeente en de was. |
| **Mindfulness** | Stress, imposter syndrome en je grenzen bewaken. |
| **Werkwoordenboek** | Al dat werkjargon, uitgelegd alsof je het aan een vriendin vraagt. |
| **Red Flags** | Waar je op let bij stages, werkgevers, recruiters en sollicitaties. |

Daarnaast biedt het platform **downloadbare templates** (cv, motivatiebrief, bedankmail, budget, weekplanner, mealplanner) die je alleen nog hoeft in te vullen.

## Functies

- **Bladeren per rubriek** met kaarten die titel en geschatte leestijd tonen.
- **Artikelpagina's** met een vaste, rustige opbouw: intro, tussenkoppen, tips en checklists.
- **Callout-blokken** in de huisstijl: Anne-Bo tips (♥), streamers/pull-quotes (★) en voorbeelden.
- **Kant-en-klare content** die eenvoudig te laden en te stylen is (zie hieronder).

## Contentstructuur

Alle artikelen zitten in **`articles.json`**. Elk artikel heeft dezelfde velden, zodat de pagina ze automatisch kan inladen en groeperen:

```json
{
  "site": "Life Cheat Codes (Adulting Academy)",
  "count": 52,
  "articles": [
    {
      "slug": "kleedtips-per-gelegenheid",
      "title": "Wat trek je aan? Kleedtips voor elke belangrijke gelegenheid",
      "category": "Dress to Impress",
      "minutes": 5,
      "html": "<p>…artikelinhoud als schone, semantische HTML…</p>"
    }
  ]
}
```

De `html` gebruikt semantische tags (`h2`, `h3`, `p`, `ul`/`ol`) plus een paar vaste klassen voor de opmaak:

| Klasse | Betekenis |
|---|---|
| `blockquote.callout--tip` | Anne-Bo tip (♥) |
| `blockquote.callout--streamer` | Pull-quote / streamer (★) |
| `blockquote.callout--example` | Voorbeeld (bijv. een voorbeeldmail) |
| `span.mark--yes` / `span.mark--no` | Goed/fout-markers (✓ / ✗) |

Het bijbehorende stijlblad **`life-cheat-codes.css`** stylet al deze elementen automatisch in de huisstijl. Render de artikel-HTML in een `<div class="lcc-article">` en de opmaak staat meteen goed.

## Projectstructuur (voorbeeld)

```
life-cheat-codes/
├── index.html              # de interactieve pagina
├── articles.json           # alle artikelen (content)
├── life-cheat-codes.css    # huisstijl-stijlblad
├── html/                   # losse HTML-fragmenten per artikel (optioneel)
├── assets/                 # afbeeldingen, logo, iconen
└── README.md
```

## Lokaal draaien

Het is een statische pagina; je hebt geen server nodig.

```bash
git clone https://github.com/<organisatie>/life-cheat-codes.git
cd life-cheat-codes
# open index.html in je browser
```

## Een artikel toevoegen of bijwerken

1. Voeg een object toe aan `articles.json` met `slug`, `title`, `category`, `minutes` en `html`.
2. Houd de bestaande callout-klassen aan, zodat de opmaak automatisch klopt.
3. Ververs de pagina — het nieuwe artikel verschijnt onder de juiste rubriek.

## Huisstijl

- **Kleuren:** donkerblauw `#1A4778` (hoofd), geel `#EDCD66` (accent), magenta `#E6007E` en lichtblauw `#6ED7DB` (steun).
- **Lettertypes:** Poppins (primair), Pulpo spaarzaam voor quotes en getallen.
- **Designelementen:** ster ★ (hoop, toekomst) en hartje ♥ (liefde, betrokkenheid).

## Tone of voice (voor wie meeschrijft)

- Altijd **Nederlands**, warm en **gelijkwaardig** — we ondersteunen de meiden, we helpen ze niet.
- **Nooit betuttelend.** Concreet, eerlijk en met lef.
- We spreken altijd over **"meiden"**, nooit over "vrouwen" of "kinderen".
- Gebruik in voorbeelden **vrouwelijke namen** en wissel rollen bewust af.
- Bij gevoelige onderwerpen (stress, faalangst, uitsluiting) verwijzen we naar de **coach** of een vertrouwenspersoon.

## Over Stichting Anne-Bo

Stichting Anne-Bo is in december 2020 opgericht door Annemieke van de Wouw, ter nagedachtenis aan haar dochter Anne-Bo, die op 19-jarige leeftijd plotseling overleed. De stichting maakt studeren toegankelijk voor jonge meiden voor wie dit anders niet mogelijk zou zijn, met studiebeurzen, boeken, een laptop én een persoonlijke coach. Inmiddels zijn er honderden studenten en coaches actief, verspreid over heel Nederland. De stichting heeft ANBI-status en CBF-erkenning.

Meer weten of steunen? Kijk op de website van Stichting Anne-Bo.

## Licentie & gebruik

De inhoud van dit platform (artikelen, teksten, huisstijl) is eigendom van **Stichting Anne-Bo** en bedoeld voor de meiden en coaches van de stichting. Neem contact op met de stichting voor hergebruik.

---

*Gemaakt met ♥ voor de meiden van Anne-Bo. Noem haar bij haar naam en zij bestaat.*
