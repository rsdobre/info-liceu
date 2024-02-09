O problemă simplă de [[Backtracking|backtracking]] de pe #pbinfo asemănătoare cu [[Paranteze]]. [Link](https://www.pbinfo.ro/probleme/3919/back-me)
# Cerința
> Se citesc două numere naturale `n` și `m`. Afișați în ordine lexicografică toate cuvintele care sunt formate din `n` litere `E` și `m` litere `M` cu proprietatea că nu există mai mult de două litere `M` alăturate și nici mai mult de două litere `E` alăturate.
# Explicație
Practic, condițiile ca să punem o literă pe o poziție sunt următoarele:
- Numărul de litere folosite deja este mai mic decât numărul de litere cerut (`nre<n` respectiv `nrm<m`)
	- Dacă suntem pe pozițiile 1 și 2 nu mai trebuie să verificăm literele anterioare
	- Altfel, dacă ultimele 2 litere sunt diferite putem să punem și `E` și `M`
	- Dacă ultimele două litere sunt identice trebuie să punem cealaltă literă
- Dacă nu există posibilitatea de a pune literele în acest fel, programul nu va mai intra în condițiile logice, nu se va mai autoapela funcția și `exista` rămâne `false`, se va afișa `IMPOSIBIL`
# Soluția:
```cpp
#include <iostream>
using namespace std;
int n, m;
char s[29];
bool exista = 0;
void generare(int nre, int nrm, int pas) {
    if (pas == n + m + 1) {
        exista = 1;
        cout << s + 1 << endl;
    } else {
        if (nre<n&&(pas <= 2 || s[pas - 1] != s[pas - 2] ||
            (s[pas - 1] == s[pas - 2] && s[pas - 1] != 'E'))) {
            s[pas] = 'E';
            generare(nre + 1, nrm, pas + 1);
        }
        if (nrm<m&&(pas <= 2 || s[pas - 1] != s[pas - 2] ||
            (s[pas - 1] == s[pas - 2] && s[pas - 1] != 'M'))) {
            s[pas] = 'M';
            generare(nre, nrm + 1, pas + 1);
        }
    }
}
int main() {
    cin >> n >> m;
    generare(0, 0, 1);
    if (!exista)
        cout << "IMPOSIBIL";
}
```
## Varianta din curs:
- Ține cont de literele rămase în apelarea funcției prin `cntE` și `cntD`
- Folosește vectorul `x[]` pentru a stoca răspunsul "codat", în cifrele 0 și 1
- La afișare folosește [[Ternary Expression|ternary expression]] pentru a decide dacă afișează `E` sau `M` pentru valoarea respectivă
- Condițiile sunt un pic diferit exprimate, dar reformulate
![[Pasted image 20240204212151.png|800]]