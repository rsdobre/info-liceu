# Definiție
Definiția simplă: arborele este un [[Grafuri neorientate|graf neorientat]] [[Grafuri#Graf conex|conex]] care nu conține [[Grafuri neorientate#Ciclu|cicluri]].
![[Pasted image 20240210001637.png|300]]
Arborele este un graf neorientat [[Grafuri#Graf conex|conex]] în care unul din [[Grafuri neorientate#Nod|noduri]] este desemnat [[#Rădăcina|rădăcină]]. Nodurile pot fi așezate pe [[#Niveluri|niveluri]] începând cu rădăcina care este plasată pe nivelul 1.
Nu există o regulă pentru cum se alege rădăcina, îl alegem noi sau ni se dă în problemă.
-  Într-un arbore cu $n$ [[Grafuri neorientate#Nod|noduri]] avem $n-1$ [[Grafuri neorientate#Muchie|muchii]].
- Un arbore este un graf conex și minimal cu această proprietate; dacă s-ar mai elimina o muchie, graful nu ar mai fi conex.
- Un arbore este un graf aciclic și maximal cu această proprietate; dacă s-ar mai adăuga o muchie, s-ar obține un ciclu.
## Rădăcina
Rădăcina este un nod special  care generează așezarea unui arbore pe [[#Niveluri|niveluri]]. Această operație se efectuează în funcție de [[Grafuri neorientate#Lungimea unui lanț|lungimea lanțurilor]] prin care celelalte noduri sunt legate de rădăcină.
## Niveluri
Nivelul unui [[Grafuri neorientate#Nod|nod]] este dat de [[Grafuri neorientate#Lungimea unui lanț|lungimea lanțului]] până la [[#Rădăcina|rădăcină]] +1
## Descendent
Într-un arbore [[Grafuri neorientate#Nod|nodul]] $y$ este descendent al nodului $x$ dacă este situat pe un [[#Niveluri|nivel]] mai mare decât nivelul lui $x$ și există un [[Grafuri neorientate#Lanț|lanț]] care le unește și nu trece prin [[#Rădăcina|rădăcină]].
### Descendent direct (fiu)
Într-un arbore [[Grafuri neorientate#Nod|nodul]] $y$ este descendent direct (fiu) al nodului $x$ dacă este situat pe [[#Niveluri|nivelul]] imediat următor lui $x$ și există [[Grafuri neorientate#Muchie|muchie]] între $x$ și $y$.
## Ascendent
Într-un arbore cu rădăcină [[Grafuri neorientate#Nod|nodul]] $x$ este ascendentul nodului $y$ dacă este situat pe un [[#Niveluri|nivel]] mai mic decât al lui $y$ și există un [[Grafuri neorientate#Lanț|lanț]] care le unește și nu trece prin [[#Rădăcina|rădăcină]].
### Ascendent direct (părinte)
Într-un arbore [[Grafuri neorientate#Nod|nodul]] $y$ este ascendent direct (părinte) al nodului $x$ dacă este situat pe [[#Niveluri|nivelul]] imediat superior (cu număr de ordine mai mic) lui $y$ și există [[Grafuri neorientate#Muchie|muchie]] între $y$ și $x$.
Practic daca $y$ este descendentul (direct) al lui  $x$, $x$ este ascendentul (direct) al lui $y$
## Frați
Într-un arbore [[Grafuri neorientate#Nod|nodul]] $x$ este fratele nodului $y$ dacă au același [[#Ascendent direct (părinte)|părinte]] (ascendent direct).
## Frunză
Într-un arbore cu rădăcină nodul $x$ este frunză dacă nu are nici un [[#Descendent|descendent]] (implicit nu are nici un [[#Descendent direct (fiu)|fiu sau descendent direct]])
