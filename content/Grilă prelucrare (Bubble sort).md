#grile #UBB 
![[Pasted image 20240205213419.png|800]]
# Explicatie
- În primul rând trebuie să recunoaștem că în interiorul lui "Dacă" se face o [[Interschimbarea a 2 variabile#Interschimbare prin înmulțire|interschimbare prin înmulțire]]. 
- Apoi trebuie să recunoaștem că funcția execută un [[Metoda bulelor|bubble sort]], alterat pe [[Vectori|vectorul]]l `x`. Ne dăm seama că este [[Metoda bulelor|bubble sort]] și  nu [[Sortare prin selecție|selection sort]] pentru că "Pentru" din interior nu are legătură (nu începe de la `k+1`) cu cel din exterior. 
- Trebuie să evaluăm dacă elementele sunt sortate crescător sau descrescător, ceea ce ne putem da seama din condiția lui "Pentru", unde dacă `x[i]>x[i+1]`, atunci se efectuează [[Interschimbarea a 2 variabile|interschimbarea]], deci [[Vectori|vectorul]] se sortează crescător.
- Rămâne doar să ne dam seama ce se întămplă cu `n`, iar cum `p` începe de la 1, și se incrementează de `n-1` ori, `p` ajunge să aibă valoarea `n`, iar `n` primește `p`, deci `n` rămâne neschimbat.
# Răspunsuri
A. `x` se sortează crescător, deci <mark style="background: #FF5582A6;">FALS</mark>
B. `x` se sortează crescător, deci <mark style="background: #FF5582A6;">FALS</mark>
C. `x` se sortează crescător, deci <mark style="background: #BBFABBA6;">ADEVĂRAT</mark>
D.  `n` rămâne neschimbat, deci <mark style="background: #FF5582A6;">FALS</mark>