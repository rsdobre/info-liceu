
Complexitatea spațiu se exprimă în general identic cu [[Complexitatea de timp|cea de timp]] sub forma $O(x)$ unde $x$ reprezintă numărul total de variabile pe care programul nostru le va stoca. $x$ nu este exprimat niciodată ca valoare absoluta ci mai mult ca si o sumă de alte variabile care reprezintă dimensiunile datelor de intrare ale programului. Exemplu: $O(n + m)$ reprezintă faptul ca programul nostru va retine $n + m$ variabile unde $n$ si $m$ sunt dimensiunile datelor de intrare (în general acest exemplu semnifică reținerea a 2 vectori de $n$ și, respectiv, $m$ elemente). 

La examene, din [[#Complexitatea de spațiu la nivel de liceu|diverse motive]] nu prea se dă complexitatea de spațiu.

Vezi regulile pentru [[Notația O|notația O]]
# Tipuri de complexități
- $O(1)$ se numește complexitate constantă. Se utilizează doar variabile simple.
- $O(n)$ se numește complexitate liniară. Se utilizează un vector cu $n$ elemente.
- $O(n\times m)$ sau $O(n^2)$ se numește complexitate pătratică. Se utilizează o matrice cu $n\times m$ elemente.
- $O(2^n)$ se numește complexitate exponențială. Se utilizează pentru memorarea arborilor de intervale (depășește programa de admitere/liceu).
# Erori
"Caught fatal signal 11" este în general eroarea semnalată de evaluatorul de probleme in momentul in care complexitatea spațiu este prea mare, adică intenționam să folosim mai multa memorie decât ne este alocată.

# Complexitatea de spațiu la nivel de liceu
În general la liceu când avem nevoie să stocăm un număr $n$ de valori într-un vector, ne uităm la limitele problemei. Dacă vedem că problema precizează $1\leq n \leq 1000$ noi declarăm scriem următoarea secvență de cod:
```cpp
int v[1001], n;
cin >> n;
for(int i=1; i<=n; i++)
	cin >> v[i];
```
Problema este că, deși noi vom folosi doar primele $n$ valori din vector, compilatorul va aloca întotdeauna $1001$ elemente în memorie. Astfel, noi am avea o complexitate practică constantă, de $O(1001)=O(1)$. Asta face imposibilă analizarea complexității de spațiu.
Ulterior, la facultate, vom învăța metode de alocare dinamică a memoriei (nu `int v[n]` care este nonstandard), iar complexitatea de spațiu va căpăta un sens practic.