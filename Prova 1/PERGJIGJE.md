# Përgjigjet — Prova 1

## P1.7

Çfarë bën box-sizing: border-box? Jep një shembull nga faqja jote që përfshin width, padding dhe border. Përgjigju në 2–3 fjali.

Përgjigjja ime: Me box-sizing: border-box, width dhe height e elementit përfshijnë edhe padding-un dhe border-in, kështu që ato nuk i shtohen gjerësisë së dhënë. Në faqen time, .cards ka padding: 2rem dhe border: 2px solid navy; me border-box dhe max-width: 100%, gjerësia totale nuk e kalon 100% të ekranit (p.sh. 328px në 360px). Pa border-box, 100% + 64px padding + 4px border do të dilnin jashtë dhe do të shkaktonin scroll horizontal, siç ndodhte me width: 900px.

## P1.8

Pse përdoret a për lidhjen Detaje, ndërsa button për një veprim si “Shfaq/Fshih tekstin”? Referoju një lidhjeje nga faqja jote. Nuk duhet të implementosh buton ose JavaScript.

Përgjigjja ime: Elementi a përdoret për lundrim, pra të çon në një vend tjetër: lidhja `<a href="#info">Detaje</a>` në secilën kartë të çon te seksioni #info, ndryshon URL-në (#info) dhe aktivizohet me Enter. Elementi button përdoret për një veprim në të njëjtën faqe pa lundruar, si “Shfaq/Fshih tekstin”; aktivizohet me Enter dhe Space, dhe lexuesit e ekranit e njoftojnë si “button”. Kështu përdoruesi e di nëse do të shkojë diku tjetër apo do të ndodhë diçka në faqe.
