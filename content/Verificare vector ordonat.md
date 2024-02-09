Se folosește [[Divide et Impera]] pentru a verifica daca un vector este ordonat. Este foarte important că nu se verifica doar dacă prima jumătate si a doua jumătate sunt ordonate, ci trebuie sa verificam și dacă numerele de la "granița" dintre cele doua secvențe sunt crescătoare.
```cpp
bool verif_ord(int a[], int st, int dr){
    if(st == dr)
        return true;
    int mij = (st + dr) / 2;
    return verif_ord(a, st, mij) && verif_ord(a, mij + 1, dr) && a[mij] <= a[mij + 1];
}
```