Graf = orice mulțime finită $V$ prevăzută cu o relație binară internă $E$. Notăm graful cu $G=(V,E)$
Noțiunile de [[Grafuri orientate#Vârf|vârf]] și [[Grafuri neorientate#Nod|nod]] sunt echivalente (dar cele de [[Grafuri orientate#Arc|arc]] și [[Grafuri neorientate#Muchie|muchie]] nu sunt).
# Tipuri de grafuri
[[Grafuri orientate]]
[[Grafuri neorientate]]
[[Arbori]]
# Terminologie comună
Un [[Grafuri neorientate#Lanț|lanț]], [[Grafuri orientate#Drum|drum]], [[Grafuri neorientate#Ciclu|ciclu]] sau [[Grafuri orientate#Circuit|circuit]]:
- are lungimea egală cu numărul de [[Grafuri neorientate#Muchie|muchii]] sau [[Grafuri orientate#Arc|arce]]
- este simplu dacă nu repetă [[Grafuri neorientate#Muchie|muchii]] sau [[Grafuri orientate#Arc|arce]]
- este compus dacă repetă [[Grafuri neorientate#Muchie|muchii]] sau [[Grafuri orientate#Arc|arce]] (dacă nu este simplu, este compus)
- este elementar dacă nu repetă [[Grafuri neorientate#Nod|noduri]] sau [[Grafuri orientate#Vârf|vârfuri]] și implicit nu repetă [[Grafuri neorientate#Muchie|muchii]] sau [[Grafuri orientate#Arc|arce]] (în cazul [[Grafuri neorientate#Ciclu|ciclurilor]] și [[Grafuri orientate#Circuit|circuitelor]] se repetă evident primul și ultimul nod)
- dacă este elementar, este implicit și simplu, dar nu și invers
## Graf parțial
Dacă dintr-un graf $G=(V,E)$ se elimină **cel puțin o [[Grafuri neorientate#Muchie|muchie]]/[[Grafuri orientate#Arc|arc]]** atunci noul graf $G'=(V,E'), E'\subset E$ se numește graf parțial al lui $G$. Deci putem elimina și toate muchiile și vom obține graful $G'=(V,\varnothing)$ (numit și [[#Graf nul|graf nul]]), care este și el un graf parțial al lui $G$. Graful inițial este și el graf parțial al lui însuși deoarece $E\subset E$
Fie $m$ numărul de muchii/arce al unui graf, numărul total de grafuri parțiale este suma numărului de grafuri cu $0,1,2,...,m$ muchii/arce eliminate. Deci formula este aceasta:
$C_m^0+C_m^1+...+C_m^m=2^m$ (vezi [[Combinări#^e79dc2|calculul numărului de submulțimi]]). 
Precizare: nu este relevant numărul de noduri/vârfuri
## Subgraf
Dacă dintr-un graf $G=(V,E)$ se elimină **[[Grafuri neorientate#Nod|noduri]]/[[Grafuri orientate#Vârf|vârfuri]]** (se pot elimina și 0 noduri) împreună cu [[Grafuri neorientate#Muchie|muchiile]]/[[Grafuri orientate#Arc|arcele]] incidente lui, atunci noul graf $G'=(V',E'),\ E'\subseteq E,\ V'\subseteq V$ se numește subgraf al lui $G$. 
- [ ] fix this when clear (inclus sau egal, sau inclus și inegal)
**ATENȚIE**: [[Graful vid]]
Fie un graf cu $n$ noduri/vârfuri, numărul total de subgrafuri este suma numărului de subgrafuri cu $0,1,2,3,...,n-1$ noduri/vârfuri eliminate. Deci formula este aceasta: $C_n^0+C_n^1+C_n^2+...+C_n^{n-1}=2^n-1$ (vezi [[Combinări#^e79dc2|calculul numărului de submulțimi]]). 
Precizare: nu este relevant numărul de muchii/arce.
## Graf conex
Graful conex este un graf $G=(V,E)$ în care pentru orice pereche de noduri $(v,w),\ v,w\in V$ există un [[Grafuri neorientate#Lanț|lanț]]/[[Grafuri orientate#Drum|drum]] care le unește
## Graf complet
Graful $G$ se numește graf complet dacă oricare două [[Grafuri neorientate#Nod|noduri]]/[[Grafuri orientate#Vârf|vârfuri]] distincte ale sale sunt [[Grafuri neorientate#Adiacența|adiacente]] (în cazul [[Grafuri orientate#comp|grafului orientat]] complet vom folosi definiția de pe pbinfo pentru [[Grafuri orientate#Adiacență|adiacență]])
Numărul muchii într-un [[Grafuri neorientate#Graf complet|graf complet neorientat]] cu $n$ noduri este $\frac{n(n-1)}{2}$. În cazul [[Grafuri orientate#Graf complet|grafului orientat complet]] nu putem ști numărul de arce.
## Graf nul
$G=(V,\varnothing)$
Graful nul este graful în care nu există [[Grafuri neorientate#Muchie|muchii]]/[[Grafuri orientate#Arc|arce]], sau în care mulțimea  muchiilor este vidă $E=\varnothing$.
A nu fi confundat cu cu [[Graful vid|graful vid]].
[[#Graf complementar|Graful complementar]] al grafului nul este [[#Graf complet|graful complet]].
## Graf complementar
Fie $G=(V,E)$ un graf. Se numește graf complementar al grafului $G$, graful $G'=(V,E')$ cu proprietatea că două noduri $i$ și $j$ sunt [[Grafuri neorientate#Adiacența|adiacente]] în $G'$ dacă și numai dacă nu sunt adiacente în $G$. Cu alte cuvinte, dacă am considera graful complet $G=(V,E'')$ , $E'\cap E=\varnothing\ \text{și}\ E'\cup E=E''$
Atenție: acest concept nu prea se aplică [[Grafuri orientate|grafurilor orientate]].
## Componenta conexă
Componenta conexă este un [[#Subgraf|subgraf]] al grafului de referință, maximal în raport cu proprietatea de conexitate (între oricare 2 vârfuri există un lanț). Sunt considerate componente conexe și nodurile izolate.
Practic este o componentă conexă când nu mai putem alege încă un [[Grafuri neorientate#Nod|nod]]/[[Grafuri orientate#Vârf|vârf]] care să fie legat de celelalte. Putem spune că sunt "insulele" din graful de referința
Graful de mai jos are 3 componente conexe
![[graph (8).png|500]]
## Hamiltonian
- [[Grafuri neorientate#Lanț elementar|Lanțul]] sau [[Grafuri orientate#Drum elementar|drumul]] elementar care conține toate [[Grafuri neorientate#Nod|nodurile]]/[[Grafuri orientate#Vârf|vârfurile]] se numește hamiltonian.
- [[Grafuri neorientate#Ciclu elementar|Ciclul]] sau [[Grafuri orientate#Circuit elementar|circuitul]] elementar care conține toate [[Grafuri neorientate#Nod|nodurile]]/[[Grafuri orientate#Vârf|vârfurile]] se numește hamiltonian.
- Graful care conține un **[[Grafuri neorientate#Ciclu elementar|ciclu]] sau [[Grafuri orientate#Circuit elementar|circuit]]** hamiltonian se numește hamiltonian.
### Condiție de suficiență
Dacă $G$ este un graf cu $n\geq 3$ [[Grafuri neorientate#Nod|noduri]]/[[Grafuri orientate#Vârf|vârfuri]] astfel încât gradul oricărui [[Grafuri neorientate#Nod|nod]]/[[Grafuri orientate#Vârf|vârf]] verifică inegalitatea $gr(x)\geq \frac{n}{2}$ rezultă că $G$ este graf hamiltonian.
Este foarte rar folosită, nu se întâmplă des ca un graf hamiltonian să îndeplinească această condiție (este suficientă, **nu necesară**)
## Eulerian
- [[Grafuri neorientate#Lanț simplu|Lanțul]] sau [[Grafuri orientate#Drum simplu|drumul]] simplu care conține toate [[Grafuri neorientate#Muchie|muchiile]]/[[Grafuri orientate#Arc|arcele]] se numește eulerian.
- [[Grafuri neorientate#Ciclu simplu|Ciclul]] sau [[Grafuri orientate#Circuit simplu|circuitul]] simplu care conține toate [[Grafuri neorientate#Muchie|muchiile]]/[[Grafuri orientate#Arc|arcele]] se numește eulerian.
- Graful care conține un **[[Grafuri neorientate#Ciclu elementar|ciclu]] sau [[Grafuri orientate#Circuit elementar|circuit]]** eulerian se numește eulerian.
### Condiție necesară și suficientă
#### Pentru graf neorientat
Un [[Grafuri neorientate|graf neorientat]] este eulerian dacă și numai dacă:
- Este [[#Graf conex|conex]]
- Oricare [[Grafuri neorientate#Nod|nod]] al său are [[Grafuri neorientate#Grad|gradul]] par
#### Pentru graf orientat
Un [[Grafuri orientate|graf orientat]] este eulerian dacă și numai dacă:
- Este conex
- Oricare [[Grafuri orientate#Vârf|vârf]] are [[Grafuri orientate#Grad interior|gradul interior]] egal cu [[Grafuri orientate#Grad exterior|gradul exterior]]


- [ ]  📅 2024-02-11 de completat cu noțiuni de pe [pbinfo](https://www.pbinfo.ro/?pagina=articole&subpagina=afisare&id=810)
- [ ] ⏫  De clarificat situația [[Graful vid|grafului vid]]