# Pergjigjet - Varianti C

Gr.3 - Elmond Vishi

## P1.7

Shpjego box-sizing: border-box me width, padding dhe border nga kodi yt.

Pergjigjja ime: Me `* { box-sizing: border-box; }` gjeresia (width) e nje elementi perfshin edhe padding-un dhe border-in. Ne kodin tim `.members` ka `width: 100%`, `padding: 1rem` dhe `border: 2px solid navy`. Me border-box, kutia mbetet gjithsej 100% e gjeresise se prindit, sepse padding dhe border hyjne brenda kesaj vlere. Pa border-box (content-box) gjeresia reale do te ishte 100% + 2rem padding + 4px border, pra paneli do te dilte jashte ekranit ne 360 px dhe do te shkaktonte scroll horizontal.

## P1.8

Pse "Me shume" eshte lidhje dhe jo button? Kur do te perdorje button? Nuk kerkohet implementim butoni ose JS.

Pergjigjja ime: "Me shume" e con perdoruesin ne nje vend tjeter (te seksioni #kontakti), pra eshte lundrim, dhe per lundrim perdoret `<a href>`. Lidhja ka URL, mund te hapet me Enter, ruhet ne historikun e shfletuesit (butoni Back punon) dhe lexuesit e ekranit e njoftojne si "link". Button do ta perdorja per nje veprim ne te njejten faqe qe nuk ndryshon adresen, p.sh. dergimi i nje formulari, hapja/mbyllja e nje menuje ose shtimi i nje vullnetari ne liste.
