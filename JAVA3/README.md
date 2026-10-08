# Java III — Klinika e CSS: shpëto afishen

Afishe për klubin e debatit (HTML + CSS i jashtëm, vetëm front end).

## Skedarët

- `index.html` — struktura e afishes (titull, datë, vend, përshkrim, lidhje regjistrimi).
- `style.css` — variablat (`:root`), faqja, etiketat, butoni, `focus-visible`.
- `gabime.css` — diagnoza dhe riparimi i dy gabimeve (komentet brenda skedarit).
- Asete lokale: nuk ka. Ikonat janë shenja teksti (✓ ! ◎).

## Si i plotëson kërkesat

1. **Afishja** me titull, datë, vend, përshkrim dhe lidhje regjistrimi.
2. **CSS i jashtëm**, klasa të ripërdorshme (`.tag`, `.btn`, `.poster`) dhe variabla (`--accent`, `--space-2` etj.).
3. **Tri etiketa** që nuk bazohen vetëm në ngjyrë: tekst + shenjë + stil kufiri
   (falas = kufi i plotë ✓, vende të kufizuara = kufi me pika !, online = kufi i dyfishtë ◎).
4. **gabime.css** i riparuar pa `!important`.
5. **Fokusi**: `a:focus-visible` dhe `.btn:focus-visible` kanë unazë 3px dhe halo të bardhë.

## width, padding, border dhe box-sizing

Me `content-box` (parazgjedhja), `width` mat vetëm përmbajtjen, ndaj gjerësia reale
është `width + padding + border`. Në `gabime.css`: 700 + 2×80 = 860px.
Me `box-sizing: border-box` (vendosur me `*` në `style.css`), `width` përfshin edhe
padding-un dhe border-in, ndaj kutia nuk bëhet kurrë më e gjerë se `width`.

## Rastet e pranimit

- [x] CSS ngarkohet nga skedarë të veçantë.
- [x] Paneli nuk del nga ekrani 360 px (`width: 100%`, `max-width: 700px`, `border-box`).
- [x] Teksti lexohet mbi sfond (#17263c mbi të bardhë) dhe fokusi shihet me Tab.

## Reflektim individual

Rregulli `#poster` fitoi në kaskadë, sepse selektori me ID ka specifikë më të lartë
(1,0,0) se selektori me klasë (0,1,0). Specifika vlerësohet para renditjes në skedar.
Rezultati ishte tekst i bardhë mbi sfond i bardhë. E zgjidha duke hequr `#poster` dhe
duke e lënë vetëm `.poster`, kështu që nuk kishte nevojë për `!important`.

## Dorëzimi

```bash
git add JavaIII/
git commit -m "Java III: Klinika e CSS"
git rev-parse HEAD   # kjo është SHA-ja që dorëzohet në LMS
```
