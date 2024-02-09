Căutarea binară se poate face atât iterativ cât și [[Recursivitate|recursiv]] folosind [[Divide et Impera]], pentru a determina dacă un număr există, sau pentru a determina poziția unui număr într-un vector [[Sortare|sortat]] anterior. Ea are complexitate $O(log_2\ (n) )$

Varianta cu while, care returnează poziția:

```cpp
int cautarebinara(int n, int a[], int val) {
    int st = 0, dr = n-1, mij;
    while (st <= dr) {
        mij = (st + dr) / 2;
        if (a[mij] == val)
            return mij;
        else if (a[mij] <= val)
            st = mij + 1;
        else
            dr = mij - 1;
    }
    return mij;
}
```

Varianta cu [[Divide et Impera]], care confirma prezenta
```cpp 
bool cb(int a[], int st, int dr, int val){
    if(st == dr)
        return a[st] == val;
    int mij = (st + dr) / 2;
    if(a[mij] == val)
        return true;
    if(a[mij] < val)
        return cb(a, mij + 1, dr, val);
    return cb(a, st, mij - 1, val);
}
```
 Ambele variante pot returna atât poziția cât și confirma prezența
