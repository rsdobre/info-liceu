Este o metodă mai scurtă de a face un `if else`. Practic este o metodă de linearizare a unei structuri alternative. Se folosește și în pseudocod, pentru [[Programa de admitere UBB 2024|admiterea de la UBB]].
De exemplu
```cpp
if(condiție)
	exec1;
else
	exec2;
```
Devine
```cpp
(condiție) ? exec1 : exec2;
```
Ea este rareori folosită pentru că:
- Nu este foarte ușor de înțeles
- Permite executarea unei singure comenzi în fiecare ca
Ea poate fi folosită și pentru a returna valori conform condiției;
```cpp
d = (d==2) ? 3 : d+2;
```
În situația de mai sus, dacă `d` este 2, primește valoarea `3` altfel, crește cu 2. Tradus în `if else` ar arăta așa.
```cpp
if(d==2)
	d=3;
else
	d=d+2;
```