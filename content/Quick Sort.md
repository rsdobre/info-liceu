Este un algoritm de [[Sortare|sortare]] de tip [[Divide et Impera]], în loc, adică nu folosește vectori auxiliari ca [[Merge Sort]]. [[Complexitatea de timp|Complexitatea medie]] este de $O( n\times \log_2 n)$, dar complexitatea în cazul unui vector ordonat la [[Quick Sort]] crește la $O(n^2)$ ([[#Complexitate timp|vezi mai multe explicații]])
# Funcționare
Fiind vorba de [[Divide et Impera]], evident algoritmul sortează intervale din șirul nostru. Spre deosebire de [[Merge Sort]], unde sortam jumătăți de șir, aici vom efectua un sortare după un **pivot**. După ce alegem un pivot, încercăm să îl aducem la poziția lui finală, mai exact, toate elementele din stânga lui să fie mai mici, iar toate elementele din dreapta să fie mai mari. După ce ducem pivotul pe poziția lui, reapelăm QuickSort pentru cele 2 intervale din stânga și dreapta.

Practic partea grea la QuickSort nu este algoritmul propriu-zis, ci găsirea poziției finale a pivotului. Funcția QuickSort va arăta astfel:
```cpp
void QuickSort(int st, int dr){
    if(st < dr){
        int pindex = partitie(st, dr);
        QuickSort(st, pindex - 1);
        QuickSort(pindex + 1, dr);
    }
}
```
După cum vedem, `pindex` primește valoarea returnată de funcția `partitie(st, dr);`. Dar ce face mai exact această funcție? Ea mută elementele din șirul dat, ca cele din stânga pivotului să fie mai mici ca el și cele din dreapta să fie mai mari, iar apoi returnează poziția la care se află acest pivot. După cum vedem mai jos, la final, șirul va fi sortat
![[Quick Sort 2024-02-11 13.40.35.excalidraw.svg]]
%%![[Quick Sort 2024-02-11 13.40.35.excalidraw|800]]%%
Să analizăm cum funcționează această funcție `partitie`:
- Declarăm variabila `pivot` (față de care vom face comparațiile) cu valoarea ultimului element (ea poate să fie orice valoare din șir, dar e un pic mai ușor de înțeles algoritmul când e ultima).
- Declarăm variabila `poz` ca prima poziție din șir
- Parcurgem șirul până la penultima valoare inclusiv
	- Dacă valoarea curentă este mai mică ca pivotul efectuăm interschimbare între ea și valoarea de la `poz`, și incrementăm `poz` pentru a trece la următoarea. Dacă este mai mică, o lăsăm acolo, iar când vom găsi o valoare care este mai mică decât `pivot`.
- La final, interschimbăm ultima valoare (pivotul) cu valoarea de la `poz`, pentru a pune pivotul pe poziția sa finală, iar apoi returnăm `poz`.
Pentru a înțelege mai bine procesul am executat algoritmul pas cu pas pe un șir oarecare:

%%![[Quick Sort 2024-02-11 14.27.19.excalidraw|800]]%%
![[Quick Sort 2024-02-11 14.27.19.excalidraw.svg]]
Secvența de cod:
```cpp
int partitie(int st, int dr){
    int pivot = a[dr];
    int poz = st;
    for(int i = st; i < dr; ++i){
        if(a[i] <= pivot){
            swap(a[i], a[poz]);
            poz++;
        }
    }
    swap(a[dr], a[poz]);
    return poz;
}
```
# Analiza complexității
## Complexitate spațiu
[[Complexitatea de spațiu]] este dezbătută, există estimări pentru $O(1)$ deoarece nu folosește vectori auxiliari, alții spun că are complexitate $O(\log_2 n)$ din cauza stivei, iar unii spun că are complexitate $O(n)$. Oricum ar fi, este general acceptat că folosește mai puțin spațiu ca [[Merge Sort]].
## Complexitate timp
[[Complexitatea de timp]] pentru acest algoritm este foarte interesantă. În cazul mediu vom avea jumătate din elemente mai mici ca pivotul și jumătate din elemente mai mari ca pivotul, iar acest lucru ar însemna că noi am face $\log_2 n$ apeluri recursive ale funcției `partitie`, iar funcția `partitie` are o complexitate liniară $O(n)$, rezultând o complexitate în cel mai bun caz de $O(n \times\log_2 n)$. Aceeași complexitate apare și în cazul mediu, deoarece, statistic vorbind, este cel mai probabil ca pivotul să fie aproape de mijloc.

Problema apare în cazul unui șir sortat, unde am folosi `partitie` de $n$ ori, pe șiruri doar cu 1 element în minus, deci am avea o complexitate de $O\left(\frac{n(n-1)}{2}\right)$ care se aproximează la $O(n^2)$. Evident pentru a evita astfel de cazuri putem folosi o varietate de metode, cum ar fi alegerea pivotului în mijloc, amestecarea șirului înainte de sortare, etc.