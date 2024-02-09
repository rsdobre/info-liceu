# Terminologie
## Definiție
Graf orientat = un [[Grafuri|graf]] $G=(V,E)$ în care relația binară nu este simetrică: $\forall (v,w)\in E,\not\rightarrow \exists (w,v)\in E$
## Vârf
Vârf = element al mulțimii $V$, unde $G=(V,U)$ este un graf orientat
### Vârf izolat
Un vârf este izolat dacă are [[#Grad|suma gradelor]] 0
Definiție alternativă: un vârf cu gradul 0
### Vârf terminal
Un vârf este terminal dacă are [[#Grad interior|gradul interior 1]] și [[#Grad exterior|gradul exterior]] 0, practic dacă poți intra și nu mai poți ieși
Definiție alternativă: un vârf cu [[#Grad|gradul]] 1
## Arc
Arc = element al mulțimii $E$, ce descrie o relație existentă între 2 [[#Vârf|vârfuri]] din $V$, unde $G=(V,E)$ este un graf orientat
### Extremitățile unui arc
Pentru arcul $(v,w)$ se numesc extremități ale sale nodurile $v$ și $w$
- $v$ se numește extremitate (vârf) inițială, iar $w$ extremitate (vârf) finală
- $v$ este predecesorul lui $w$, iar $w$ este succesorul lui $v$
Arcele sunt parcurse numai în direcția dată de relația $\text{predecesor}\to\text{succesor}$.
## Adiacență
Vârful $w$ este adiacent cu vârful $v$ dacă perechea $(v,w)\in E$, deci  $w$ este adiacent cu $v$ doar dacă este succesorul acestuia.
Această definiție este controversată deoarece pe [pbinfo](https://www.pbinfo.ro/articole/509/grafuri-orientate#intlink-1) se definesc 2 noduri ca fiind adiacente dacă există un [[#Arc|arc]] în orice sens între ele.
- [ ] ⏫ de clarificat definiția adiacenței in graful orientat
## Incidență
Un arc este incident cu un nod dacă îl are pe acesta ca extremitate. Arcul $(v,w)$ este incident cu $v$ respectiv $w$.
În cazul grafurilor orientate apar relațiile de [[#Incidența spre interior|incidență spre interior]] respectiv [[#Incidența spre exterior|exterior]].
### Incidența spre interior
Un [[#Arc|arc]] este incident spre interior cu un [[#Vârf|vârf]] dacă îl are pe acesta ca vârf terminal. Practic un arc este incident spre interior dacă acesta "intră" într-un vârf. Arcul $(v,w)$ este incident spre interior cu vârful $w$.
### Incidența spre exterior
Un [[#Arc|arc]] este incident spre exterior cu un [[#Vârf|vârf]] dacă îl are pe acesta ca vârf inițial. Practic un arc este incident spre interior dacă acesta "pleacă" sau "iese" dintr-un vârf. Arcul $(v,w)$ este incident spre exterior cu vârful $v$.
## Grad
### Grad interior
În cazul unui graf orientat fiecare vârf $v$ are are asociat un număr numit grad interior care este egal cu numărul de arce care îl au pe $v$ ca [[#Extremitățile unui arc|vârf terminal]] (numărul de arce [[#Incidența spre interior|incidente spre interior]]), sau numărul de noduri care îl au pe $v$ ca [[#Extremitățile unui arc|succesor]], sau numărul de [[#Extremitățile unui arc|predecesori]] ai lui $v$.
### Grad exterior
În cazul unui graf orientat fiecare vârf $v$ are are asociat un număr numit grad exterior care este egal cu numărul de arce care îl au pe $v$ ca [[#Extremitățile unui arc|vârf inițial]] (numărul de arce [[#Incidența spre interior|incidente spre interior]]), sau numărul de noduri care îl au pe $v$ ca [[#Extremitățile unui arc|predecesor]], sau numărul de [[#Extremitățile unui arc|succesori]] ai lui $v$.
## Drum
Drumul este o secvență de [[#Vârf|vârfuri]] ale unui graf orientat $G=(V,E)$ legate fiecare de următorul printr-un [[#Arc|arc]]. Trebuie să poată fii parcurs pe direcția de mers a [[#Arc|arcului]], în secvența $\text{predecesor}\to\text{succesor}$.
$w_1,w_2,w_3,...,w_n$ cu proprietatea că $(w_i, w_{i+1})\in E,\ 1\leq i \lt n$
$(3,5,4)$ este un drum, dar $(1,6,2)$ nu este un drum
![[graph (6).png|500]]
Proprietățile drumurilor și tipurile lor sunt [[Grafuri#Terminologie comună|similare]] cu cele ale [[Grafuri neorientate#Lanț|lanțurilor]].
### Lungimea unui drum
Lungimea unui drum este numărul de arce din care este format
### Drum simplu
Drumul simplu este drumul care conține numai [[#Arc|arce]] distincte
### Drum compus
Drumul compus este drumul care nu este format numai din [[#Arc|arce]] distincte. Practic, dacă un drum nu este simplu, este compus.
### Drum elementar
Drumul elementar este drumul care are numai [[#Vârf|vârfuri]] distincte
## Circuit
Circuitul este un drum în care primul vârf coincide cu ultimul.
### Lungimea unui circuit
Lungimea unui circuit este egală cu numărul de [[#Arc|arce]].
### Circuit simplu
Circuitul simplu este un circuit în care nu se repetă nici un [[#Arc|arc]].
### Circuit compus
Circuitul compus este un circuit care nu este format numai din [[#Arc|arce]] distincte. Practic dacă un ciclu nu este [[#Circuit simplu]], este compus.
### Circuit elementar
Un circuit este elementar dacă este format doar din [[#Vârf|vârfuri]] distincte, excepție făcând primul și ultimul. Implicit asta înseamnă că nu se repetă nici un [[#Arc|arc]]. Deci orice circuit elementar este implicit și [[#Circuit simplu|simplu]], dar nu și invers.
### Bucla
Bucla este un circuit format dintr-un singur arc și implicit un singur nod. Aceasta este reprezentată în $E$ ca $(v,v)$.
## Tipuri de grafuri orientate
### Graf turneu
- [ ] 🔼 de completat definiția de pe [pbinfo](https://www.pbinfo.ro/articole/509/grafuri-orientate#intlink-9)
### Graf orientat [[Grafuri#Hamiltonian|hamiltonian]]
- [[Grafuri orientate#Drum elementar|Drumul]] elementar care conține toate [[Grafuri orientate#Vârf|vârfurile]] se numește hamiltonian.
- [[Grafuri orientate#Circuit elementar|Circuitul]] elementar care conține toate [[Grafuri orientate#Vârf|vârfurile]] se numește hamiltonian.
- Graful care conține un **[[#Circuit elementar|circuit]]** hamiltonian se numește hamiltonian.
### Condiție de suficiență
Dacă $G$ este un graf cu $n\geq 3$ [[Grafuri orientate#Vârf|vârfuri]] astfel încât gradul oricărui [[Grafuri orientate#Vârf|vârf]] verifică inegalitatea $gr(x)\geq \frac{n}{2}$ rezultă că $G$ este graf hamiltonian.
Este foarte rar folosită, nu se întâmplă des ca un graf hamiltonian să îndeplinească această condiție (este suficientă, **nu necesară**)
### Graf orientat eulerian
- [[Grafuri orientate#Drum simplu|Drumul]] simplu care conține toate [[Grafuri orientate#Arc|arcele]] se numește eulerian.
- [[Grafuri orientate#Circuit simplu|Circuitul]] simplu care conține toate [[Grafuri orientate#Arc|arcele]] se numește eulerian.
- Graful care conține un **[[Grafuri orientate#Circuit elementar|circuit]]** eulerian se numește eulerian.
#### Condiție necesară și suficientă
Un [[Grafuri orientate|graf orientat]] este eulerian dacă și numai dacă:
- Este conex
- Oricare [[Grafuri orientate#Vârf|vârf]] are [[Grafuri orientate#Grad interior|gradul interior]] egal cu [[Grafuri orientate#Grad exterior|gradul exterior]]