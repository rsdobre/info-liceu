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
# Tipuri de grafuri neorientate
## Graf regulat
Graful regulat este graful în care toate [[#Nod|nodurile]] au același grad. Deci și un graf fără muchii $G=(V,\varnothing)$ este graf regulat.
## Graf complet
Graful complet este un graf în care există o [[#Muchie|muchie]] între oricare 2 [[#Nod|noduri]]. 
Numărul de muchii ale unui graf complet este $C_n^2=\frac{n(n-1)}{2}=$, unde $n$ este numărul de muchii.
## Graf nul
$G=(V,\varnothing)$
Graful nul este graful în care nu există [[#Muchie|muchii]]/[[Grafuri orientate#Arc|arce]], sau în care mulțimea  muchiilor este vidă $E=\varnothing$.
A nu fi confundat cu cu [[Graful vid|graful vid]].
[[#Graf complementar|Graful complementar]] al [[#Graf nul|grafului nul]] este [[#Graf complet|graful complet]]
## Graf complementar
Fie $G=(V,E)$ un graf. Se numește graf complementar al grafului $G$, graful $G'=(V,E')$ cu proprietatea că două noduri $i$ și $j$ sunt [[#Adiacența|adiacente]] în $G'$ dacă și numai dacă nu sunt adiacente în $G$. Cu alte cuvinte, dacă am considera graful complet $G=(V,E'')$ , $E'\cap E=\varnothing\ \text{și}\ E'\cup E=E''$
## Graf regulat
Un graf neorientat este numit regulat dacă toate [[#Nod|nodurile]] au același [[#Grad|grad]].
## Graf bipartit
Un graf $G=(V,E)$ este numit bipartit dacă există 2 mulțimi nevide, $A$ și $B$ astfel încât $V=A\cup B,\ A\cap B=\varnothing$ și orice muchie $u\in E$ a lui $G$ are o extremitate în $A$, iar cealaltă în $B$. Mulțimile $A$ și $B$ formează o partiție a lui $V$.
Exemplu: Graful următor este bipartit: $A=\{1,2,5,7\}$ și $B=\{3,4,6\}$
![[Pasted image 20240210000831.png|400]]
### Graf bipartit complet
Un graf bipartit $G=(V,E)$ este numit bipartit complet dacă pentru oricare 2 [[#Nod|noduri]] $x\in A,\ y\in B$ există în graf muchia $(x,y)\in E$.
Exemplu: graful următor este bipartit complet.
![[Pasted image 20240210001355.png|400]]
## Arbore
Se numește [[Arbori|arbore]] un graf [[Grafuri#Graf conex|conex]] și [[#Ciclu|aciclic]].
![[Pasted image 20240210001646.png|300]]
- Un [[Grafuri#Graf parțial|graf parțial]] care este arbore se numește arbore parțial.
- Un graf care nu conține cicluri se mai numește pădure. Într-o pădure fiecare [[Grafuri#Componenta conexă|componentă conexă]] este un [[Arbori|arbore]].
Vezi [[Arbori|articoulul despre arbori pentru mai multe detalii]].
## Graf neorientat [[Grafuri#Hamiltonian|hamiltonian]]
- [[#Lanț elementar|Lanțul]] elementar care conține toate [[#Nod|nodurile]] se numește hamiltonian.
- [[#Ciclu elementar|Ciclul]] elementar care conține toate [[#Nod|nodurile]] se numește hamiltonian.
- Graful care conține un **[[#Ciclu elementar|ciclu]]** hamiltonian se numește hamiltonian.
### Condiție de suficiență
Dacă $G$ este un graf cu $n\geq 3$ [[#Nod|noduri]] astfel încât gradul oricărui [[#Nod|nod]] verifică inegalitatea $gr(x)\geq \frac{n}{2}$ rezultă că $G$ este graf hamiltonian.
Este foarte rar folosită, nu se întâmplă des ca un graf hamiltonian să îndeplinească această condiție (este suficientă, **nu necesară**)
## Graf neorientat [[Grafuri#Eulerian|eulerian]]
- [[#Lanț simplu|Lanțul]]  simplu care conține toate [[#Muchie|muchiile]] se numește eulerian.
- [[#Ciclu simplu|Ciclul]]  simplu care conține toate [[#Muchie|muchiile]] se numește eulerian.
- Graful care conține un **[[#Ciclu elementar|ciclu]] eulerian se numește eulerian**.
### Condiție necesară și suficientă
Un graf neorientat este eulerian dacă și numai dacă:
- Este [[#Graf conex|conex]]
- Oricare [[#Nod|nod]] al său are [[#Grad|gradul]] par

# Reprezentarea grafurilor neorientate
## Matricea de adiacență
Pentru un graf neorientat $G=(V,E)$ cu $n$ [[#Nod|noduri]], matricea de adiacență $A$ este o [[Matrice|matrice]] cu $n$ linii și $n$ coloane și elemente din $\{0,1\}$ (este booleană), cu $A_{i,j} = \begin{cases} 1 & \text{dacă } (i,j) \in E \\0 & \text{dacă } (i,j) \notin E \end{cases}$
**Exemplu:** Pentru graful neorientat de mai jos avem următoarea matrice de adiacență:
![[Pasted image 20240210002801.png|300]] $A = \begin{pmatrix}0 & 1 & 0 & 0 & 1 \\1 & 0 & 0 & 1 & 1 \\0 & 0 & 0 & 0 & 0 \\0 & 0 & 0 & 1 & 1 \\1 & 1 & 0 & 1 & 0 \\\end{pmatrix}$
### Observații
- matricea de adiacență este simetrică față de diagonala principală;
- elementele de pe [[Matrice#Diagonala principală|diagonala principală]] sunt `0`;
- gradul unui [[#Nod|nod]] `x` este egal cu numărul de elemente `1` de pe linia (sau coloana) `x`;
- suma tuturor elementelor din matricea de adiacență a unui graf neorientat este egală cu dublul numărului de [[#Muchie|muchii]] din graf.
## Lista de muchii
Lista de muchii a unui graf neorientat reprezintă o mulțime ce conține toate muchiile din graf.

Pentru graful de mai jos, lista de muchii este: $E=\{(1,2),(1,5),(2,5),(4,5)\}$
![[Pasted image 20240210003339.png|300]]
Atenție: în lista de muchii nu sunt reprezentate [[#Nod izolat|nodurile izolate]].
### Reprezentare în memorie
Pentru reprezentarea în memorie putem folosi:
- un tablou unidimensional cu elemente de tip `struct {int I,J;}`
- două tablouri unidimensionale cu elemente de tip `int`
- o listă alocată dinamic
- etc.

## Liste de adiacențe
Pentru un graf neorientat cu $G=(V,E)$ se va memora numărul de [[#Nod|noduri]] $n$ și apoi, pentru fiecare nod $x$, lista vârfurilor [[#Adiacența|adiacente]] cu $x$, adică a nodurilor $y$ cu proprietatea că există [[#Muchie|muchia]] $(x,y)\in E$.

Pentru graful de mai jos, listele de adiacență sunt:
![[Pasted image 20240210003721.png|300]] 
```
1: 2 5
2: 1 5
3: vidă
4: 5
5: 1 2 4
```
### Reprezentarea în memorie
La reprezentarea în memorie trebui avut în vedere că dimensiunile listelor de vecini sunt variabile. De aceea, este [[Complexitatea de spațiu|ineficientă]] (dar posibilă cu o matrice de `n` linii și `n-1` coloane) utilizarea unor tablouri alocate static. Astfel, putem folosi:
- un șir de `n` tablouri unidimensionale alocate dinamic;
- un șir de `n` vectori din STL;
- un șir de `n` liste simplu (dublu) înlănțuite alocate dinamic.