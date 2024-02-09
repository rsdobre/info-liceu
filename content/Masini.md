Problema [#91 - Masini](https://www.pbinfo.ro/probleme/91/masini)de pe #pbinfo este un exemplu foarte simplu în care se folosește [[Metoda Greedy|metoda greedy]].

# Cerința
> În curtea unui atelier de reparaţii auto, sunt `n` mașini care trebuie sa fie reparate. Deoarece nu sunt suficienți mecanici, în fiecare moment de timp se poate lucra doar la o singură mașină.
> Cunoscând timpul necesar pentru repararea fiecărei mașini, scrieți un program care calculează numărul maxim de mașini care pot fi reparate într-un interval de timp `T`.

Practic, noi ne propunem să reparăm cât mai multe mașini într-un interval de timp, ca să avem loc de alte mașini. Este evident un proces "lacom" pentru că în mod normal un service auto ar funcționa pe procesul de "primul venit primul servit". 

Natural soluția este ca la fiecare pas să reparăm mașina care are timpul de reparare cel mai mic. Deci evident, sortăm vectorul cu timpii de reparație și îl parcurgem crescător, scăzând din `T` până nu mai avem timpul pentru a face următoarea reparație.

# Soluția
```cpp
#include <fstream>
#include <algorithm>
using namespace std;
ifstream fin ("masini.in");
ofstream fout ("masini.out");

int main(){
    int T, n;
    fin >> n >> T;
    int v[n];
    for (int i = 0; i < n; i++)
        fin >> v[i];
    sort(v, v+n);
    int cnt;
    for (cnt = 0; cnt < n && T-v[cnt]>=0; cnt++)
        T-=v[cnt];
    fout << cnt;
}
```
## Varianta din curs
![[Pasted image 20240204231118.png|800]]
![[Pasted image 20240204231144.png|800]]
Diferențele sunt următoarele:
- Se implementează sortarea ca subprogram prin [[metoda bulelor|Metoda bulelor]]
- Indexarea de la 1
- Folosește un `while` pentru parcurgerea vectorului sortat