#pbinfo 
Problema [#344 - Paranteze](https://www.pbinfo.ro/probleme/344/paranteze) de pe #pbinfo se rezolvă cu [[Backtracking|backtracking]]
# Cerința

>Se dă un număr natural par `n`. Generați toate șirurile de `n` paranteze rotunde care se închid corect.
# Explicație
Condițiile ca un șir să fie corect sunt următoarele(considerăm $pd$ numărul de paranteze deschise și $pi$ numărul de paranteze închise):
- Dacă $pi=pd$ nu mai putem închide o paranteză nouă (secvența `(()))(` este invalidă), deci putem închide paranteze doar când $pi\lt pd$
- La final $pi=pd=\frac{n}{2}$
Deci structura funcției de generare este următoarea:
- Dacă am ajuns cu pasul, `k` la n, afișăm
- Altfel 
	- Dacă `pd<n/2` adăugăm o `(` și reapelăm funcția trecând la următorul pas și incrementând `pd`
	- Dacă `pi<n/2` și `pi<pd` adăugăm o `)` și reapelăm funcția trecând la următorul pas și incrementând `pi`
# Soluția:
```cpp
#include <fstream>
using namespace std;
ifstream fin("paranteze.in");
ofstream fout("paranteze.out");
char s[20];
int n;
void generare(int k, int pi, int pd) {
    if (n == k) {
        fout << s << endl;
    } else {
        if (pd < n / 2) {
            s[k] = '(';
            generare(k + 1, pi, pd + 1);
        }
        if (pi < n / 2 && pi < pd) {
            s[k] = ')';
            generare(k + 1, pi + 1, pd);
        }
    }
}

int main() {
    int n;
    fin >> n;
    generare(n, 0, 0, 0);
}
```
## Varianta din curs
![[Pasted image 20240204213213.png|800]]
## Varianta ineficientă din curs, care folosește funcția [[Backtracking#Fără `verif()` sau `valid()`|Valid()]]
![[Pasted image 20240204213451.png|800]]