

# Funcții predefinite
## Copiere
Copiază șirul de caractere stocat la adresa `src` în adresa `dest`
```cpp
strcpy(dest, src);
```
### Ștergerea caracterelor prin copiere
- [ ] 📅 2024-02-13 de explicat în detaliu cum se transferă memoria și cum funcționează adresele
Există 2 variante similare pentru ștergere, ambele se bazează pe aritmetică cu pointeri.
În variantele mai vechi de C++ ne puteam folosi de funcția `strcpy()` pentru a șterge un caracter de pe poziția `i` din `sir` astfel
```cpp
strcpy(sir+i, sir+i+1)
```
Această variantă nu mai este validă în versiunile recente de C++, are un comportament nedefinit. De aceea vom folosi un șir de caractere auxiliar, `aux`, pentru această operație, similar cu [[Interschimbarea a 2 variabile#Interschimbare clasică (metoda paharelor)|metoda paharelor pentru interschimbarea variabilelor]].
```cpp
char aux[strlen(sir)-ii];
strcpy(aux,sir+i+1);
strcpy(sir+i, aux);
```