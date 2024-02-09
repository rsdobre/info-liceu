[problema #1660 - Fotbal](https://www.pbinfo.ro/probleme/1660/fotbal) de pe #pbinfo.
# Cerința
> Se dau `2` numere naturale reprezentând scorul în timpul actual. Să se determine în câte moduri se poate ajunge de la `0-0` la acel scor.
# Explicație
Varianta naivă folosește apeluri recursive repetate:
```cpp
#include <iostream>
using namespace std;

int scor(int x, int y){
    if(x==0||y==0)
        return 1;
    return scor(x-1,y)+scor(x, y-1);
}

int main(){
    int a, b;
    cin >> a >> b;
    cout << scor(a,b);
}
```
În varianta aceasta funcția recursivă va face foarte mulți pași, de exemplu pentru `10-10` se fac `369511` pași. Acest număr imens este dat de faptul că programul nostru va repeta apeluri identice, așa cum se vede și în arborele de apeluri pentru poza de mai jos, pentru cazul `3-3`.
![[PuRsRJhVW8.png|800]]
Pentru a evita această problema vom folosi [[Memoizare|memoizarea]], memorând rezultatele calculate într-o matrice, iar când avem nevoie a 2-a oară de o valoare, o vom prelua din matrice, fără să mai calculăm din nou. Pentru a le memora vom folosi o matrice în care `scor[i][j]` reprezintă valoarea apelului `scor_rec(i,j)` sau numărul de moduri de a ajunge la `i-j`. Astfel în cazul calculului scorului `10-10` numărul de autoapeluri scade de la `360000` la doar `120`. Programul cu memorizare arată astfel:
# Soluția:
```cpp
#include <iostream>
using namespace std;

long long scor[1001][1001];

int scor_rec(int x, int y){
    if(x==0||y==0)
        return 1;
    if(scor[x-1][y]==0)
        scor[x-1][y]=scor_rec(x-1, y);
    if(scor[x][y-1]==0)
        scor[x][y-1]=scor_rec(x, y-1);
    return scor[x-1][y]+scor[x][y-1];
}

int main(){
    int a,b;
    cin >> a >> b;
    cout << scor_rec(a,b);
}
```
