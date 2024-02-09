Problema [#353 - Spectacole](https://www.pbinfo.ro/probleme/353/spectacole) de pe #pbinfo este un exemplu de problemă de dificultate medie-grea în care se folosește [[metoda greedy|Metoda Greedy]].
# Cerința
>La un festival sunt programate `n` spectacole. Pentru fiecare se cunoaște momentul de început și momentul de sfârșit, exprimate prin numere naturale. Un spectator dorește să urmărească cât mai multe spectacole în întregime.
>Determinați numărul maxim de spectacole care pot fi urmărite, fără ca acestea să se suprapună.
# Explicație
Prima variantă la care ne gândim ar fii să sortăm spectacolele în funcție de ora de început. Această variantă ar fi greșită deoarece s-ar putea să alegem un spectacol care începe mai devreme, dar se termină mult mai târziu, iar noi ne-am ocupa o bucată mare din timp cu un singur spectacol.

Așadar, varianta mai bună este următoarea:
- Sortăm crescător spectacolele după ora de final
- Parcurgem orele de final în ordine crescătoare
	- Verificăm dacă ora de început a următorului spectacol din vector este `>=` ca ora de final a spectacolului la care "suntem"
		- Dacă da, "mergem" la spectacolul respectiv și actualizăm contorul
		- Altfel, verificăm următorul spectacol
Astfel, prin acest procedeu întotdeauna intrăm la spectacolele care se termină cel mai repede, eliberând mai mult timp pentru următoarele spectacole.
# Soluția
```cpp
#include <fstream>
using namespace std;
ifstream fin("spectacole.in");
ofstream fout("spectacole.out");
struct spectacol {
    int start, final;
} a[101];
int n;
void sortare(spectacol a[], int n) {
    for (int i = 1; i < n; i++)
        for (int j = i + 1; j <= n; j++)
            if (a[i].final > a[j].final)
                swap(a[i], a[j]);
}
int main() {
    fin >> n;
    for (int i = 1; i <= n; i++)
        fin >> a[i].start>> a[i].final;
    sortare(a, n);
    int cnt=1;
    int ora_fin=a[1].final;
    for (int i = 2; i <= n; i++)
        if(ora_fin<=a[i].start)
            cnt++, ora_fin=a[i].final;
   fout << cnt; 
}
```
## Varianta din curs
![[Pasted image 20240205164923.png|800]]
- Diferențele sunt minime, doar în numele variabilelor
- Ambele variante folosesc [[Sortare prin selecție]]