# Testet — Prova 1

**Varianti A — Klub shkencor**

Plotëso kolonën e rezultatit real pasi ta provosh faqen. Mos shkruaj “kalon” pa e kontrolluar.

| Testi | Rezultati i pritur | Rezultati real |
|---|---|---|
| Tri karta | Titujt dhe kategoritë përputhen me variantin | Kalon: Teleskopi, Uji, Energjia, secila me “Kategoria: Shkencë”. |
| Menuja Programi / Info | Çdo lidhje ka seksionin e vet objektiv | Kalon: #programi dhe #info ekzistojnë si ID të seksioneve. |
| Detaje në secilën kartë | Hap seksionin #info | Kalon: të tri lidhjet “Detaje” kanë href="#info". |
| Gjerësia 360 px | Një kolonë, pa scroll horizontal | Kalon: një kolonë; scrollWidth (345) ≤ gjerësia e dritares (360), pa scroll horizontal. |
| Gjerësia 1000 px | Tri kolona | Kalon: media query min-width 800px jep repeat(3, 1fr), tri kolona. |
| Tekst i gjatë në kartë | Përmbajtja qëndron brenda në 360 px | Kalon: me AktivitetStudentorPaHapesira123… teksti thyhet brenda kartës (overflow-wrap: anywhere); teksti u hoq pas provës. |
| Tastiera Tab dhe Enter | Fokusi shihet; Enter aktivizon lidhjen | Kalon: me Tab shfaqet outline 3px navy (a:focus-visible); Enter hap objektivin e lidhjes. |
