# Robot Sort Race — 50 algoritmes

`sorting-race-video.html` is één zelfstandig bestand met:

- een **zoeklijst van 50 sorteeralgoritmes**;
- **toevoegen en weghalen** door op een algoritme te klikken;
- een race waarin **alle gekozen algoritmes tegelijk** hetzelfde rijtje getallen sorteren;
- een **automatische video-opname** (MP4 of WebM) van titel, countdown, race en uitslag.

Alles werkt offline. Je hebt geen Node, Python of FFmpeg nodig.

---

## 1. Snel starten

1. Dubbelklik op `sorting-race-video.html`.
2. Open het bestand met **Microsoft Edge** of **Google Chrome**.
3. Kies hierboven je algoritmes (standaard staan de vijf bekendste al aan).
4. Klik op **▶ Start race** of druk op **Space**.
5. Wil je een video? Klik op **⏺ Record video**.

---

## 2. Algoritmes kiezen

Bovenaan staat een zoeklijst met alle 50 namen.

| Actie | Hoe |
|---|---|
| Zoeken | Typ in **Zoek algoritme…** (bijv. `quick`, `heap`, `radix`, `bogo`) |
| Uitleg lezen | Klik op een algoritme; onder de lijst verschijnt hoe het werkt, met de complexiteit |
| Toevoegen | Klik op een algoritme met **+** |
| Weghalen | Klik op een geselecteerd algoritme met **✓** |
| Alles toevoegen | Knop **Alles toevoegen** (50 races tegelijk) |
| Terug naar 5 | Knop **Standaard 5** |
| Leegmaken | Knop **Leegmaken** |
| Weergave | **Weergave: passend** = hele race in beeld; **Weergave: 100%** = echte grootte, scrollen |

Eén klik doet dus twee dingen: het algoritme wordt **toegevoegd of weggehaald**
én de **uitleg** verschijnt in het vak onder de lijst. Daar zie je:

- **hoe het algoritme werkt** in gewone taal;
- **beste geval / gemiddeld / slechtste geval** (Big-O);
- **extra ruimte** die het nodig heeft;
- een **gele notitie** als de animatie een vereenvoudigde variant gebruikt.

Tijdens een race kun je nog steeds op elk algoritme klikken om de uitleg te lezen;
de selectie wordt dan niet aangepast. Het laatst bekeken algoritme krijgt een
gouden streepje links.

De lijst is doorzoekbaar op naam, key en categorie (Exchange, Merge, Partition,
Distribution, Heap, Network, Fun, …).

Het canvas wordt automatisch **zo hoog als nodig**:

- 5 algoritmes → 1280 × 710;
- 50 algoritmes → 1280 × 3100 (een lang canvas, precies zoals gevraagd).

De video wordt altijd op de volledige canvasgrootte opgenomen, ook als je op het
scherm “passend” bekijkt.

---

## 3. De race

Elk algoritme krijgt **exact dezelfde geschudde array** (`1 … n`) en doet per tick
**één zichtbare stap**:

- geel ringetje = vergelijking;
- rood ringetje = swap of verschuiving;
- gekleurde streep = actief bereik (merge/quick);
- gouden driehoek = pivot (quick sort);
- ballen schuiven met een kleine boog naar hun nieuwe plek.

Snelheid en aantal items:

| Control | Betekenis |
|---|---|
| **Speed** | milliseconden per stap; standaard **500 ms**, van 60 tot 1200 ms |
| **Items** | 5–12 ballen per robot; standaard **8** |
| **▶ Start race / Space** | start een nieuwe race |
| **⏸ Pause / Space** | pauzeert of hervat |
| **↺ Reset** | nieuwe willekeurige array |
| **⏺ Record video** | start een race en neemt hem op |

De klok start bij **GO!** en telt alleen tijdens de race. Pauzes en de countdown
tellen niet mee.

---

## 4. Scorebord en uitslag

Per robot zie je tijdens de race:

```
22 cmp · 12 moves
step 24 · 12.0 s
```

Na de finish:

```
✓ 13.5 s · 27 steps
```

In het eindklassement staan alle deelnemers op volgorde van **stappen** (bij een
gelijke stand: vergelijkingen, daarna moves). De kolommen zijn:

| # | ALGORITHM | TIME | STEPS | COMPARES | MOVES |
|---|---|---|---|---|---|
| 1 | Quick Sort | 10.5 s | 21 | 13 | 8 |
| 2 | Merge Sort | 11.5 s | 23 | 16 | 7 |

De uitslag blijft ongeveer **5 seconden** staan (8 seconden bij meer dan 12
algoritmes), zodat hij in de video zichtbaar is.

---

## 5. Video opnemen

1. Klik op **⏺ Record video**.
2. **Houd het tabblad zichtbaar.** Niet minimaliseren en niet naar een ander tabblad
   schakelen: de browser stopt dan met frames aanleveren.
3. Wacht op de countdown, de race en de uitslag.
4. De video downloadt automatisch naar je **Downloads**-map.
   - `.mp4` als je browser/encoder dat ondersteunt;
   - anders `.webm`.
5. Als de download geblokkeerd is, klik je op de bestandsnaam onder de canvas.

De opname is **1280 × H** (H = 710 bij 5 algoritmes, 3100 bij 50). De titel, de
countdown, alle banen en de uitslag zitten erin.

### WebM → MP4

- **Clipchamp** (Windows): nieuw project → video slepen → exporteren als MP4.
- **VLC**: Media → Convert / Save → MP4.
- **HandBrake**.

In Clipchamp kun je ook direct een **voice-over** opnemen boven de video.

> Bij een zeer hoog canvas (50 algoritmes) kan de MP4-encoder van je browser
> weigeren. Het programma valt dan automatisch terug op WebM. Dat is normaal.

---

## 6. Welke algoritmes zijn “echt” en welke vereenvoudigd?

Alle 50 komen uit de gevraagde lijst en kunnen sorteren. Voor de onbekendere of
exotische algoritmes is gekozen voor een **vereenvoudigde maar correcte animatie**.
Ze sorteren dezelfde array en halen de finish.

Echt geïmplementeerd (met eigen stappen):

Bubble, Selection, Insertion, Merge, Quick, Heap, Shell, Counting, Radix, Bucket,
Tim, Tree, Cocktail Shaker, Comb, Gnome, Odd-Even, Bitonic, Pancake, Bogo, Bozo,
Stooge, Slow, Bead/Gravity.

Vereenvoudigd (duidelijke variant van een verwant algoritme):

- IntroSort, Sample Sort, Parallel Quick Sort, Dual-Pivot Quick Sort → Quick Sort;
- Strand, Library, Patience → Insertion Sort;
- Smoothsort, Weak Heap → Heap Sort;
- Pigeonhole → Counting Sort;
- Flash → Bucket Sort;
- American Flag, Burstsort → Radix Sort;
- Odd-Even Merge, Sorting Network, Bose-Nelson → Odd-Even Sort;
- Parallel Merge, GrailSort, WikiSort, External Merge, Polyphase Merge → Merge Sort;
- Cartesian Tree → Tree Sort;
- Cycle, Tournament, Replacement Selection, Sleep, Spaghetti → Selection Sort.

**Vangnet:** als een algoritme na **220 stappen** nog niet klaar is (bijvoorbeeld
Stooge of Slow Sort), maakt de robot de race af met een gegarandeerde selectiesort.
Zo blijft de video nooit hangen. Je kunt die grens aanpassen met `MAX_STEPS`.

---

## 7. Hoe pas je het aan?

Open `sorting-race-video.html` in een teksteditor (Notepad, VS Code, …). De
belangrijkste instellingen staan bovenin het `<script>`-blok. Daarna opslaan en de
pagina verversen.

### Standaardselectie

```js
const DEFAULT_KEYS = ["bubble", "selection", "insertion", "merge", "quick"];
let selectedKeys = new Set(DEFAULT_KEYS);
```

Zet hier andere keys in. De keys staan in `ALGO_LIBRARY`.

### Algoritme toevoegen of aanpassen

In `ALGO_LIBRARY` staat elk algoritme als:

```js
{ key: "mijnsort", name: "Mijn Sort", tag: "Fun", blurb: "korte uitleg", impl: mijnSort }
```

- `key` moet uniek zijn;
- `name` is de naam in de zoeklijst en op de baan;
- `tag` is de categorie (verschijnt klein in de lijst);
- `blurb` is de regel onder de naam;
- `impl` is de generatorfunctie.

Daarna hoef je alleen nog een generator te schrijven:

```js
function* mijnSort(a) {
  for (let i = 0; i < a.length; i++) {
    // yield { type: "compare", i, j }
    // yield { type: "swap", i, j }
  }
}
```

Beschikbare operaties:

| Operatie | Betekenis |
|---|---|
| `{ type: "compare", i, j }` | twee ballen vergelijken (gele ringen) |
| `{ type: "swap", i, j }` | twee ballen wisselen (rode ringen) |
| `{ type: "rotate", from, to }` | één bal naar voren schuiven (merge) |
| `range: [lo, hi]` | optioneel: actief bereik onderstrepen |
| `pivot: index` | optioneel: gouden driehoek bij quick sort |

Belangrijk: **verander de array vóór de `yield`** van een swap. De animatie leest
namelijk direct daarna de nieuwe volgorde.

### Uitleg per algoritme

De tekst in het uitlegvak staat in `ALGO_INFO`, direct onder `ALGO_LIBRARY`:

```js
const ALGO_INFO = {
  mijnsort: {
    how: "In gewone taal: wat doet dit algoritme stap voor stap?",
    best: "O(n)", avg: "O(n log n)", worst: "O(n²)", space: "O(n)",
    note: "Optioneel: verschijnt in het geel, bijv. bij een vereenvoudigde variant.",
  },
  // … één blok per key uit ALGO_LIBRARY
};
```

De `key` moet **exact** overeenkomen met die in `ALGO_LIBRARY`. Voeg je een nieuw
algoritme toe, zet er dan ook een blok in `ALGO_INFO` bij; zonder blok blijft het
uitlegvak bij dat algoritme leeg. `note` mag je weglaten.

### Kleuren

Kleuren worden automatisch gegenereerd met de gulden-snede-hue:

```js
color: hslToHex((index * 137.508) % 360, 72, 62)
```

Wil je een vaste kleur? Zet in het algoritme-object bijvoorbeeld:

```js
color: "#ff7b54"
```

### Snelheid en aantal items

```html
<input id="speed" type="range" min="60" max="1200" step="20" value="500">
<input id="size" type="range" min="5" max="12" step="1" value="8">
```

```js
let speed = 500;      // ms per stap
let itemCount = 8;
```

Verander steeds **beide** plekken (de slider en de JS-variabele) als je een andere
startwaarde wilt.

### Lane-hoogte en canvas-hoogte

In `applyLayout()`:

```js
LANE_H = n <= 8 ? 108 : n <= 14 ? 92 : n <= 24 ? 76 : n <= 36 ? 64 : 56;
LANE_GAP = n <= 8 ? 4 : 3;
H = Math.max(420, LANE_TOP + n * (LANE_H + LANE_GAP) + 46);
```

Meer ruimte per baan? Verhoog de waarden. Meer dan 50? De canvas wordt dan nog
hoger; let op de maximale hoogte die je videokaart/encoder aankan.

### Countdown, uitslag en vangnet

```js
countdownEnd = countdownStart + 3300;                  // 3 · 2 · 1 · GO!
stopTimer = setTimeout(stopRecording, ranking.length > 12 ? 8000 : 5200);
const MAX_STEPS = 220;                                  // daarna selectiesort
```

### Opnamekwaliteit

```js
const stream = canvas.captureStream(30);                // 30 fps
videoBitsPerSecond: 10_000_000                          // 10 Mbps
```

Meer kwaliteit = groter bestand. Voor 1280 × 3100 is 10 Mbps redelijk; verhoog naar
20 Mbps als je meer detail wilt.

### Weergave op het scherm

```css
canvas { max-height: 78vh; }
```

`Weergave: passend` gebruikt deze limiet. `Weergave: 100%` zet `max-height` uit en
laat je scrollen. De opname gebruikt altijd de volledige resolutie.

---

## 8. Hoe het technisch werkt

- Elk algoritme is een **JS-generator** die de array sorteert en per stap één
  `compare`, `swap` of `rotate` yieldt.
- De race-engine doet per tick (`speed` ms) voor **elke** onafgemaakte robot precies
  één stap. Daardoor is de race eerlijk: zelfde array, zelfde aantal beurten.
- Ballen zijn objecten met een `value` en een getween-de `x`. Een swap verandert de
  array; de ballen krijgen een nieuwe target-positie en schuiven er in 80% van een
  tick naartoe.
- Counting/radix/bucket berekenen eerst de doelvolgorde en voeren die daarna uit met
  zichtbare swaps, zodat de ballen hun identiteit houden.
- De uitslag sorteert op stappen, dan vergelijkingen, dan moves.
- Opnemen gebeurt met `canvas.captureStream()` + `MediaRecorder`; wat je op de
  canvas ziet, zit dus precies in de video.

---

## 9. Problemen oplossen

| Probleem | Oplossing |
|---|---|
| “No video data was captured” | Tabblad zichtbaar houden, niet minimaliseren; Edge/Chrome gebruiken |
| Geen MP4 | Browser ondersteunt alleen WebM; converteer met Clipchamp/VLC |
| Download start niet | Klik op de bestandsnaam-link onder de canvas |
| Race duurt lang | Zet **Speed** lager (bijv. 120 ms) of kies minder algoritmes |
| Alles is piepklein | Klik **Weergave: 100%** en scroll, of kies minder algoritmes |
| Een algoritme lijkt op een ander | Dat klopt: exotische algoritmes zijn vereenvoudigd (zie §6) |

---

Veel plezier met de race! 🏁
