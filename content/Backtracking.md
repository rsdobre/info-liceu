Backtracking este un procedeu de programare pentru a determina rezultatul unei probleme, generează toate variantele posibile. De obicei este un algoritm [[Recursivitatea|recursiv]]. Este important de precizat că faptul că generează toate variantele posibile. Asta îl face un algoritm foarte lent care nu poate fi folosit pentru date de intrare foarte mari. Informaticienii il folosesc foarte mult pentru matematica, putând sa genereze toate [[Permutări#Generarea permutărilor|permutările]], [[Aranjamente||aranjamentele]], [[Combinări#Generarea combinărilor|combinările]], [[Partiții|partițiile]], etc. Deși pare un algoritm care se folosește mult pe șiruri, acesta poate fi implementat și pe [[Matrice|matrice]] pentru a determina numărul total de drumuri intre 2 poziții sau alte probleme de acest tip (sau [[Problema Damelor]]).

# De ce se numește backtracking
[[Backtracking]], tradus din engleză înseamnă "a da înapoi". Practic, la [[Backtracking|backtracking]], dacă ajungem la o valoare invalidă sau imposibilă, ne întoarcem înapoi pe arborele de apeluri. 
# Cum funcționează
Dacă suntem siguri că orice variantă care folosește o anumită valoare nu e validă, ne întoarcem înapoi și nu mai verificăm și valorile următoare (vezi pașii 1, 2 din poză). Dacă există o posibilitate să fie valid, verificăm toate posibilitățile ce urmează (vezi pașii 3-8 din poză). Întotdeauna ne întoarcem la "tatăl" din arbore și apoi verificăm și ceilalți "copii", pentru că unul poate fii varianta corectă (vezi pașii 10-12 din poză)
![[Untitled-2024-02-03-1835 1.svg|1500]]
- Se modifică ultima variabilă până nu se mai poate modifica cu valori mai mari
- Se resetează ultima valoare, se modifică penultima valoare și din nou continuă modificarea ultimei variabile până la limita superioară.
- Se resetează ultima valoare, se incrementează penultima și continuă procesul pana prima variabila ajunge la limita superioara.
![[Pasted image 20240204214717.png|800]]
# Proprietăți
- Generează întotdeauna răspunsurile în ordine lexicografică
# Fără `verif()` sau `valid()`
Se evită funcțiile de tip `verif()` sau `valid()`  pentru că [[Backtracking|backtracking]] este deja foarte ineficient și generarea soluțiilor incorecte va duce la o ineficiență și mai mare. Așadar căutăm să creăm o funcție care generează de la bun început doar răspunsuri valide.

## Exemplu
Un exemplu practic dintr-o astfel problemă cu [[Backtracking|backtracking]] îl reprezintă problema [#3169 - Plata2](https://www.pbinfo.ro/probleme/3169/plata2) de pe pbinfo unde generăm o soluție pentru a plăti o sumă specificată cu un număr de bancnote specificate cu valori specificate, folosind minim o bancnotă din fiecare. [[Plata2|Rezolvare și explicație]]

Alte probleme rezolvate "deștept" cu backtracking
[[Paranteze]]