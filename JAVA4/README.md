# Java IV — Festivali që përshtatet në çdo ekran

## Çfarë mëson

Flexbox, Grid, media queries dhe pamje responsive.

Referencë tematike: kap. 6–7 të librit.

## Skenari

Programi i një festivali shkencor duhet të lexohet si në telefon ashtu edhe në ekran të gjerë.

## Kërkesat

1. Krijo gjashtë karta aktivitetesh dhe një menu fleksibile.
2. Përdor Grid: një kolonë nën 600 px, dy nga 600 deri në 899 px dhe tri nga 900 px.
3. Kartat kanë titull, kategori, orar dhe lidhje detajesh; teksti i gjatë nuk duhet të dalë jashtë.
4. Përdor imazh fleksibël dhe mos përdor lartësi fikse për tekstin.
5. Testo në 360, 768 dhe 1280 px; ruaj rezultatet në README.

## Rastet e pranimit

- [ ] Në 360/768/1280 px shfaqen përkatësisht 1/2/3 kolona.
- [ ] Nuk ka scroll horizontal në faqen e plotë.
- [ ] Menuja mbetet e përdorshme me tastierë.

## Sfida e transferimit

Një titull 100-karakterësh duhet të përshtatet pa prishur kartën. Kjo sfidë është formuese; nuk jep bonus jashtë rubrikës.

## Dorëzimi dhe GitHub

Puno në JavaIV/ të repository-t individual. Dorëzo kodin, asetet lokale dhe README.md me: çfarë realizove, hapat e hapjes, hyrje → rezultat i pritur → rezultat i marrë për testet, përgjigjen e reflektimit dhe deklarimin e AI/burimeve. Për React dorëzo edhe package.json dhe lockfile; mos dorëzo node_modules/ ose dist/.



## Reflektim individual

Kur do të zgjidhje Flexbox dhe kur Grid?

---

# Zgjidhja

## Cfare realizova

- Menu fleksibile me Flexbox qe punon edhe me tastiere.
- Gjashte karta aktivitetesh me kategori, titull, orar dhe lidhje per detaje.
- Grid me 1 kolone nen 600 px, 2 kolona nga 600 deri ne 899 px dhe 3 kolona nga 900 px.
- Teksti i gjate thyhet brenda kartes dhe kartat nuk kane lartesi fikse.
- Imazh fleksibel qe pershtatet me ekranin.

## Hapat e hapjes

1. Hap dosjen `JAVA4/`.
2. Hap `index.html` në shfletues (dopio-klik ose „Open with Live Server” në VS Code).
3. Për testim të gjerësive: DevTools (F12) → Toggle device toolbar (Ctrl+Shift+M) → vendos gjerësinë 360 / 768 / 1280.

## Testet

Testuar në Microsoft Edge (headless) duke e ngarkuar faqen në iframe me gjerësi fikse dhe duke matur `grid-template-columns`, `scrollWidth` dhe `clientWidth`, plus kontroll vizual i pamjeve.

| # | Hyrje | Rezultati i pritur | Rezultati i marrë |
|---|-------|--------------------|-------------------|
| 1 | Gjerësi 360 px | 1 kolonë | 1 kolonë po |
| 2 | Gjerësi 768 px | 2 kolona | 2 kolona po |
| 3 | Gjerësi 1280 px | 3 kolona | 3 kolona po |
| 4 | 360 / 768 / 1280 px | Pa scroll horizontal (`scrollWidth` = `clientWidth`) | 345=345, 753=753, 1265=1265 po |
| 5 | Titull 100-karakterësh dhe fjalë shumë e gjatë pa hapësira | Teksti thyhet brenda kartës | 0 elemente dalin jashtë kartës po |
| 6 | Tab nga fillimi i faqes | „Kalo te përmbajtja” → lidhjet e menusë → „Detajet” e kartave, me kontur fokusi | __ |

## Rastet e pranimit

- [x] Në 360/768/1280 px shfaqen përkatësisht 1/2/3 kolona.
- [x] Nuk ka scroll horizontal në faqen e plotë.
- [x] Menuja mbetet e përdorshme me tastierë.

## Përgjigja e reflektimit

Flexbox do ta zgjidhja kur elementet rreshtohen në **një drejtim** dhe madhësia e tyre varet nga përmbajtja — si menuja, ku butonat kanë gjerësi të ndryshme dhe thjesht kalojnë në rresht të ri kur s’ka vend, ose brenda një karte për të shtyrë lidhjen „Detajet” në fund. Grid do ta zgjidhja kur dua kontroll në **dy drejtime** (rreshta dhe kolona njëkohësisht) dhe një strukturë të rregullt, si rrjeti i kartave, ku të gjitha kolonat duhet të kenë gjerësi të barabartë dhe numri i tyre ndryshon sipas ekranit.

## Deklarimi i AI/burimeve



