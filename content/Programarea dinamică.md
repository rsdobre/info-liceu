[[Programarea dinamică]] este un concept informatic care presupunerea calcularea a noi valori bazându-ne pe valori
precalculate. De asemenea, poate fi considerată și ca fiind o metodă de divizare a unei probleme în subprobleme, care rezolvându-le să ne ducă la rezolvarea problemei inițiale. Multe concept informatice se bazează pe [[Programarea dinamică|programare dinamică]], dar aceasta nu este predate prea amănunțit în școli pentru ca nu este un capitol care să intre la BAC sau admitere.
De exemplu, daca ma interesează să știu o anumită proprietate despre un număr `n`, este suficient să determin modul în care foarte general pot răspunde la aceeași proprietate referindu-se la o poziție `i`, cuprinsă între 1 și n.
In practica, ce vrea sa spună conceptul e că dacă ne dorim sa calculăm un rezultat pentru un întreg, trebuie să calculăm mai întâi pentru toate subproblemele problemei.
La fel ca [[Metoda Greedy]], nu este un algoritm propriu zis, ci este o metodă de gândire. 
Este deseori mult mai eficientă ca [[Metoda Greedy]].

# Exemple
## Factorial

## Sume parțiale
Dacă ne interesează suma elementelor vectorului `a[]`, putem calcula suma celor `n` elemente. Subproblema ar fi să analizăm această situație din prisma unui `i` oarecare din intervalul $\overline{1,n}$. Astfel, oricare ar fi `i`, vom știi suma primelor `i` elemente. Suma primelor `n` elemente este suma primelor `n-1` + elementul de la poziția `n`.
În loc să calculăm pentru fiecare `sp[i]` suma elementelor de la `a[1]` la `a[i]`, putem aduna `a[i]` la `sp[i-1]`
```cpp
#include <iostream>
using namespace std;
int main() {
    int n;
    cin >> n;
    int a[n + 1];
    for (int i = 1; i <= n; i++)
        cin >> a[i];
    int sp[n];
    sp[1] = a[1];
    for (int i = 2; i <= n; i++)
        sp[i] = sp[i - 1] + a[i];
}
```
Folosind vectorul de [[Programarea dinamică#Sume parțiale|sume parțiale]] putem calcula suma oricărui interval $[i,j], \forall\ i,j \in \overline{1,n}, i\leq j$ astfel: `sp[i]-sp[j-1]`
## [[Șirul lui Fibonacci]]

## [[Triunghiul lui Pascal]]