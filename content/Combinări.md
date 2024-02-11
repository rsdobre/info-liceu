[[Combinări|Combinările]] reprezintă numărul tuturor submulțimilor de $k$ elemente ale unei mulțimi cu $n$ elemente.

$C_n^k=\text{card}(M)\ \text{unde}\ M=\{c_1, c_2, ..., c_k\}\ \text{unde}\ c_i\lt c_j\ \forall i,j\in \overline{1,k}\ \text{cu}\ i\lt j\ \text{și}\ c_i \in \overline{1,n}$

[[Combinări|Combinările]]  sunt practic [[Aranjamente|aranjamente]] în care ținem cont de ordine. De exemplu $C_2^2=\frac{2!}{2!\times(2-2)!}=\frac{2}{2\times(0!)}=\frac{2}{2\times1}=1$ adică mulțimea neordonată $\{1,2\}$  , spre deosebire de [[Aranjamente|aranjamente]] unde $A_2^2=\frac{2!}{(2-2)!}=\frac{2}{0!}=\frac{2}{1}=2$ adică $(1,2)$ și $(2,1)$.  Așa că combinările sunt mulțimi neordonate, deci aproape întotdeauna $C_n^k \lt A_n^k$, excepția fiind când $k=1$, atunci $C_n^k=A_n^k$.

$C_n^k=\frac{n!}{k!\times(n-k)!}=\frac{A_n^k}{P_k}=C_{n-1}^k+C_{n-1}^{k-1}$

Ultima varianta este cea mai bună pentru programare, deoarece se folosește [[Recursivitatea|recursivitate]], față de primele 2 variante unde s-ar ajunge la numere foarte mari înainte de împărțire, care nu pot fii stocate în C++. Metoda aceasta reiese din [[Triunghiul lui Pascal]]. Evident pentru a evita calcule repetate se poate utiliza [[Memoizare|memoizarea]].

# Numărul de combinări

Metoda [[Recursivitatea|recursivă]]:
```cpp
int combinari(int n, int k){
    if(k == 0 || n == k)
        return 1;
    return combinari(n-1, k) + combinari(n-1, k-1);
}
```

# Generarea combinărilor
Pentru a face algoritmul mai ușor, considerăm că elementele din [[Combinări|combinările]] generate vor fii întotdeauna ordonate, deci modificăm [[Aranjamente#Generarea aranjamentelor|algoritmul de generarea aranjamentelor]]. Totuși nu este destul să modificăm doar condiția de afișare și să verificăm dacă elementele sunt ordonate crescător, deoarece ar fii foarte ineficient, așa că modificăm condiția `for` pentru a începe de la `i = x[pas-1]+1` . De asemenea este important să observăm că într-o [[Combinări|combinare]] nu putem avea niciodată pe poziția `pas` o valoare mai mare decât `n - (k-pas)` (De exemplu pentru $C_3^5$ nu vom avea niciodată pe poziția 1 sau 2 numărul 5), deci modificăm condiția `for` ca `i <= n - k + pas`. Pentru că le generăm în ordine nu mai avem nevoie nici de condiții suplimentare, nici de vectorul caracteristic `P[ ]` cu care verificam dacă un număr a fost folosit deja, deoarece generarea ordonată ne asigură că elementele nu se vor repeta niciodată. Astfel ajungem la cea mai bună complexitate posibilă pentru $C_n^k$ și anume $O(k\times C_n^k)$, n fiind afișările

```cpp
int n, k;
int x[11];
void afis(){
    for(int i = 1; i <= k; ++i)
        cout << x[i] << ' ';
    cout << '\n';
}
void back(int pas){
    for(int i = x[pas - 1] + 1; i <= n - (k - pas); ++i){
        x[pas] = i;
        if(pas == k)
            afis();
        else
            back(pas + 1);
    }
}
int main(){
    cin >> n >> k;
    back(1);
    return 0;
}
```

# Alte formule și explicații matematice

$C_n^k=\frac{n!}{k!\times(n-k)!}=\frac{A_n^k}{P_k},\ 0\le k \le n,\ \ n,k\in \mathbb{N}$ 

$C_n^k=C_n^{n-k}$

$C_n^k=C_{n-1}^k+C_{n-1}^{k-1}$

$C_n^0=C_n^n=1$

$C_n^1=C_n^{n-1}=n$
## Numărul de submulțimi
Numărul tuturor (inclusiv mulțimea vidă) submulțimilor dintr-o mulțime este:

$\sum\limits_{k=0}^n C_n^k=C_n^0+C_n^1+...+C_n^{n-1}+C_n^n=2^n$

Numărul de mulțimi cu 0 elemente care este calculată ca $C_n^0$ este 1, și anume mulțimea vidă $\varnothing$ Deci numărul de submulțimi nevide este:

$\sum\limits_{k=1}^n C_n^k=C_n^1+C_n^2...+C_n^{n-1}+C_n^n=2^n-1$ ^e79dc2

## [[Binomul lui Newton]] folosind combinări

$(a+b)^n=C_n^0a^nb^0+C_n^1a^{n-1}b^1+C_n^2a^{n-2}b^2+...+C_n^ka^{n-k}b^k+...+C_n^{n-1}a^1b{n-1}+C_n^na^0b^n$

Astfel formula termenului general de rang $k+1$ este: $T_{k+1}=C_n^ka^{n-k}b^k$

Sau recurent pentru rangul $k+2$: $T_{k+2}=\frac{n-k}{k+1}\times \frac{b}{a} T_{k+1}$

## Alte identități

$2^n=\sum\limits_{k=0}^n C_n^k=C_n^0+C_n^1+...+C_n^{n-1}+C_n^n$

$2^{n-1}=\sum\limits_{k=0}^{\frac{n}{2}}C_n^{2k}=C_n^0+C_n^2+C_n^4+...$

$2^{n-1}=\sum\limits_{k=0}^{\frac{n-1}{2}}C_n^{2i+1}=C_n^1+C_n^3+C_n^5+...$

$0=\sum\limits_{k=0}^{n}(-1)^kC_n^k=C_n^0-C_n^1+C_n^2-C_n^3+...+(-1)^nC_n^n$