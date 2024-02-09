# Terminologie
## Definiție
Graf neorientat = un [[Grafuri|graf]] $G=(V,E)$ în care relația binară este simetrică: $\forall (v,w)\in E\rightarrow \exists (w,v)\in E$
## Nod
Nod = element al mulțimii $V$, unde $G=(V,E)$ este un graf neorientat
### Nod izolat
Un nod cu [[#Grad|gradul]] 0
### Nod terminal
Un nod cu [[#Grad|gradul]] 1
## Muchie
Muchie = element al mulțimii $E$ ce descrie o relație existentă între două [[#Nod|noduri]], unde $G=(V,E)$ este un graf neorientat
Muchiile sunt considerate ca neavând direcție deci pot fi parcurse în ambele sensuri.
## Adiacența 
Vârfurile $w$ și $v$ sunt adiacente dacă $(v,w)\in E$. În cazul grafurilor neorientate această relație este bidirecțională deci $w$ adiacent cu $v$ $\leftrightarrow$ $v$ adiacent cu $w$. 
## Incidența
O muchie este incidentă cu un nod dacă îl are pe acesta ca extremitate. Muchia $(v,w)$ este incidentă cu $v$ respectiv $w$.
## Grad
Gradul unui nod $v$, dintr-un graf neorientat, este numărul natural ce reprezintă numărul de noduri [[#Adiacența|adiacente]] cu acesta, sau numărul de muchii [[#Incidența|incidente]].
## Lanț
Lanțul este o serie de noduri dintr-un graf neorientat $G=(V,E)$ cu proprietatea ca între oricare 2 noduri sunt [[#Adiacența|adiacente]] (există o muchie).
$w_1,w_2,w_3,...,w_n$ cu proprietatea că $(w_i,w_{i+1})\in E,\ 1\leq i\lt n$
Proprietățile lanțurilor și tipurile lor sunt [[Grafuri#Terminologie comună|similare]] cu cele ale [[Grafuri orientate#Drum|drumurilor]].
### Lungimea unui lanț
Lungimea unui lanț este numărul de [[#Muchie|muchii]] (sau $\text{numărul de noduri}-1$) din care acesta este format.
### Lanț simplu
Lanțul simplu este lanțul care conține numai [[#Muchie|muchii]] distincte.
### Lanț compus
Lanțul compus este lanțul care nu este format numai din [[#Muchie|muchii]] distincte. Practic, dacă un lanț nu este [[#Lanț simplu|simplu]], este compus.
### Lanț elementar
Este un lanț în care nu se repetă niciun [[#Nod|nod]], și implicit nicio [[#Muchie|muchie]]. Deci practic un lanț elementar este un [[#Lanț simplu|lanț simplu]], dar nu și invers.
Lanțul $(1,2,3,4,2,5)$ este [[#Lanț simplu|simplu]] dar nu este elementar, dar lanțul $(1,2,3,4)$ este atât simplu cât și elementar.
![[graph (1) 2.png|400]]
## Ciclu
Un ciclu este un [[#Lanț|lanț]] în care primul [[#Nod|nod]] coincide cu ultimul.
### Lungimea unui ciclu
Lungimea unui ciclu, la fel ca [[#Lungimea unui lanț|lungimea unui lanț]] este egală cu numărul de [[#Muchie|muchii]]. Lungimea unui ciclu nu poate fi 2.
### Ciclu simplu
Un ciclu simplu, la fel ca un [[#Lanț simplu|lanț simplu]] este un ciclu în care nu se repetă nici o [[#Muchie|muchie]].
### Ciclu compus
Ciclul compus este ciclul care nu este format numai din [[#Muchie|muchii]] distincte. Practic, dacă un ciclu nu este [[#Lanț simplu|simplu]], este compus.
Ciclul $(1,2,3,4,5,3,2,6,1)$ este compus deoarece se repetă muchia $(2,3)$
![[graph (5).png|500]]
### Ciclu elementar
Un ciclu este elementar dacă este format doar din [[#Nod|noduri]] distincte, excepție făcând primul și ultimul. Implicit asta înseamnă că nu se repetă nici o [[#Muchie|muchie]]. Deci orice ciclu elementar este implicit și [[#Ciclu simplu|ciclu simplu]], dar nu și invers.
Ciclul $(1,2,3,4,2,5,1)$ este [[#Ciclu simplu|simplu]] dar nu este și elementar, dar ciclul $(1,2,5)$ este atât simplu cât și elementar.
![[graph (2).png|500]]
## Tipuri de grafuri neorientate
### Graf regulat
Graful regulat este graful în care toate [[#Nod|nodurile]] au același grad. Deci și un graf fără muchii $G=(V,\varnothing)$ este graf regulat.
### Graf complet
Graful complet este un graf în care există o [[#Muchie|muchie]] între oricare 2 [[#Nod|noduri]]. 
Numărul de muchii ale unui graf complet este $\frac{n(n-1)}{2}$, unde $n$ este numărul de muchii.
### Graf neorientat [[Grafuri#Hamiltonian|hamiltonian]]
- [[Grafuri neorientate#Lanț elementar|Lanțul]] elementar care conține toate [[Grafuri neorientate#Nod|nodurile]] se numește hamiltonian.
- [[Grafuri neorientate#Ciclu elementar|Ciclul]] elementar care conține toate [[Grafuri neorientate#Nod|nodurile]] se numește hamiltonian.
- Graful care conține un **[[Grafuri neorientate#Ciclu elementar|ciclu]]** hamiltonian se numește hamiltonian.
#### Condiție de suficiență
Dacă $G$ este un graf cu $n\geq 3$ [[Grafuri neorientate#Nod|noduri]] astfel încât gradul oricărui [[Grafuri neorientate#Nod|nod]] verifică inegalitatea $gr(x)\geq \frac{n}{2}$ rezultă că $G$ este graf hamiltonian.
Este foarte rar folosită, nu se întâmplă des ca un graf hamiltonian să îndeplinească această condiție (este suficientă, **nu necesară**)
### Graf neorientat [[Grafuri#Eulerian|eulerian]]
- [[Grafuri neorientate#Lanț simplu|Lanțul]]  simplu care conține toate [[Grafuri neorientate#Muchie|muchiile]] se numește eulerian.
- [[Grafuri neorientate#Ciclu simplu|Ciclul]]  simplu care conține toate [[Grafuri neorientate#Muchie|muchiile]] se numește eulerian.
- Graful care conține un **[[Grafuri neorientate#Ciclu elementar|ciclu]]  eulerian se numește eulerian.
#### Condiție necesară și suficientă
Un [[Grafuri neorientate|graf neorientat]] este eulerian dacă și numai dacă:
- Este [[#Graf conex|conex]]
- Oricare [[Grafuri neorientate#Nod|nod]] al său are [[Grafuri neorientate#Grad|gradul]] par