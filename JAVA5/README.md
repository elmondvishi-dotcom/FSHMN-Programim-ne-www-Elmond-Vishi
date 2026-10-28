# Java V — Formulari i misionit sekret

## Çfarë mëson

Formularë semantikë, validim HTML dhe tabela të dhënash.

Referencë tematike: kap. 5 të librit.

## Skenari

Një klub organizon një mision në kampus dhe kërkon regjistrime të sakta, pa dërguar të dhëna reale.

## Kërkesat për studentin

1. Ndërto formular me pseudonim 3–20 karaktere, email, grup 1–5 persona, kategori dhe pranim të rregullave.
2. Çdo kontroll ka label; radio-t kanë fieldset/legend. Përdor required, type, min/max dhe minlength/maxlength.
3. Krijo tabelë me tri orare; përdor caption, th dhe scope.
4. Butoni submit demonstron validimin vendas. Me të dhëna valide kalon te pranuar.html përmes GET; shpjego se kjo nuk ruan regjistrim në server.
5. Përdor vetëm të dhëna të sajuara; shëno se vlerat GET shfaqen në URL.

## Rastet e pranimit

- [ ] Formulari bosh nuk kalon.
- [ ] Email pa format email-i dhe grup 0 ose 6 nuk kalojnë.
- [ ] Të dhënat valide çojnë te faqja e demonstrimit; tabela ka tituj kolonash.

## Dorëzimi dhe GitHub

Puno në JavaV/ të repository-t individual.

## Reflektim individual

Pse required në frontend nuk provon që të dhënat në një sistem real janë të sigurta?

---

# Zgjidhja

## Çfarë realizova

- `index.html`: formular me `method="get"` dhe `action="pranuar.html"`, me këto fusha:
  - pseudonimi: `type="text"`, `required`, `minlength="3"`, `maxlength="20"`
  - email-i: `type="email"`, `required`
  - madhësia e grupit: `type="number"`, `required`, `min="1"`, `max="5"`
  - kategoria: tri radio brenda `fieldset`/`legend`, `required`
  - pranimi i rregullave: checkbox `required`
- Çdo fushë ka `label` me `for`; shënimet ndihmëse lidhen me `aria-describedby`.
- Tabelë me tri orare, me `caption`, `th scope="col"` për kolonat dhe `th scope="row"` për rreshtat.
- `pranuar.html`: lexon vlerat nga URL-ja me `URLSearchParams` dhe i shfaq me `textContent`, që HTML-ja e futur në URL të mos ekzekutohet.
- Të dy faqet shpjegojnë që vlerat GET duken në URL dhe që asgjë nuk ruhet në server.

## Hapat e hapjes

1. Hap dosjen `JAVA5/`.
2. Hap `index.html` në shfletues (dopio-klik ose „Open with Live Server” në VS Code).
3. Plotëso formularin dhe shtyp „Dërgo regjistrimin”.

## Testet

Testet 1–4 dhe 6–9 u bënë në Microsoft Edge (headless): faqja u ngarkua në iframe, fushat u plotësuan dhe u kontrollua `form.checkValidity()`. Testi 5 duhet bërë me dorë, sepse shfletuesi e kontrollon `minlength` vetëm kur përdoruesi shkruan vetë në fushë.

| # | Hyrje | Rezultati i pritur | Rezultati i marrë |
|---|-------|--------------------|-------------------|
| 1 | Formular bosh | Nuk dërgohet | `checkValidity()` = false, po |
| 2 | Email `agjenti` (pa `@`), fushat e tjera valide | Nuk dërgohet | false, po |
| 3 | Grupi `0` | Nuk dërgohet (`min`) | false, po |
| 4 | Grupi `6` | Nuk dërgohet (`max`) | false, po |
| 5 | Pseudonimi `Bu` (2 karaktere), i shkruar me tastierë | Nuk dërgohet (`minlength`) | __ |
| 6 | Pa zgjedhur kategori | Nuk dërgohet | false, po |
| 7 | Pa pranuar rregullat | Nuk dërgohet | false, po |
| 8 | `Bufi_i_Natës`, `agjenti@shembull.test`, grupi 3, Zbulues, rregullat ✓ | Hapet `pranuar.html?pseudonimi=...&email=...&grupi=3&kategoria=zbulues&rregullat=po` | true; URL `pseudonimi=Bufi_i_Nat%C3%ABs&email=agjenti%40shembull.test&grupi=3&kategoria=zbulues&rregullat=po`, po |
| 9 | `pranuar.html?pseudonimi=<b>Bufi</b>` | Shfaqet si tekst, jo si HTML | Shfaqet `<b>Bufi</b>` si tekst, 0 elemente `<b>`, po |
| 10 | Tabela | `caption`, 4 `th scope="col"`, 3 rreshta me `th scope="row"` | 4 kolona, 3 rreshta, caption po |

## Rastet e pranimit

- [x] Formulari bosh nuk kalon.
- [x] Email pa format email-i dhe grup 0 ose 6 nuk kalojnë.
- [x] Të dhënat valide çojnë te faqja e demonstrimit; tabela ka tituj kolonash.

## Përgjigja e reflektimit

Atributi `required` dhe validimi tjetër HTML ekzekutohen në shfletuesin e përdoruesit, i cili është plotësisht nën kontrollin e tij. Atributet mund të hiqen me DevTools, formulari mund të dërgohet me `novalidate`, ose kërkesa mund të dërgohet drejtpërdrejt pa kaluar fare nga formulari, p.sh. duke shkruar me dorë `pranuar.html?grupi=99` ose me `curl`. Prandaj validimi në frontend shërben vetëm për përvojën e përdoruesit: i tregon gabimet shpejt dhe qartë. Në një sistem real serveri duhet t'i validojë sërish të gjitha të dhënat dhe t'i pastrojë para se t'i ruajë ose t'i shfaqë. Të dhënat e ndjeshme nuk duhet të dërgohen me GET, sepse përfundojnë në URL, në historikun e shfletuesit dhe në log-et e serverit.

## Deklarimi i AI/burimeve

- Kodi u gjenerua me ndihmën e Claude (Anthropic) dhe u rishikua/testua nga unë.
- Burime: MDN Web Docs (`<form>`, validimi i formularëve, `<table>` dhe `scope`, `URLSearchParams`); kap. 5 të librit të lëndës.
- Të gjitha të dhënat (pseudonimi, email-i, oraret) janë të sajuara.
