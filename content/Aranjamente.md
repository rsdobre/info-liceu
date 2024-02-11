Aranjamentele reprezintă numărul tuturor submulțimilor ordonate de $k$ elemente ale unei mulțimi cu $n$ elemente.

$A_n^k=\text{card}(M)\ \text{unde}\ M=\{\overline{c_1 c_2 c_3...c_k}\}\ \text{unde}\ c_i\neq c_j\ \forall i,j \in \overline{1,k}\ \text{cu}\ i\neq j\ \text{și}\ c_i\in\overline{1,n}$

$A_n^k=\frac{n!}{(n-k)!}=\frac{P_n}{P_{n-k}}=(k+1)\times (k+2)\times (k+3)... \times (n-2)\times (n-1)\times n = \prod\limits_{i=k+1}^n i$
[[Aranjamente|Aranjamentele]] sunt practic [[Combinări|combinări]] în care ținem cont de ordine. De exemplu $A_2^2=\frac{2!}{(2-2)!}=\frac{2}{0!}=\frac{2}{1}=2$ adică $(1,2)$ și $(2,1)$ sunt distincte, spre deosebire de [[Combinări|combinări]] unde $C_2^2=\frac{2!}{2!\times(2-2)!}=\frac{2}{2\times(0!)}=\frac{2}{2\times1}=1$ adică mulțimea $\{1,2\}$. Așa că după cum reiese și din nume a [[Aranjamente|aranjamentele]] sunt mulțimi aranjate, sau ordonate, și pentru că ținem cont de această ordine aproape întotdeauna $A_n^k \gt C_n^k$, excepția fiind când $k=1$, atunci $A_n^k=C_n^k$.

Deși folosirea permutărilor este cea mai evidenta varianta nu este și cea mai eficientă, și poate pune probleme in stocarea numerelor foarte mari in C++ (de exemplu in cazul de $A_{100}^{1}$, unde pentru a face împărțirea factorialelor se va calcula $100!$, chiar daca se $\div$ ulterior la $99!$, și rezultă 100), așa ca este mai ușor sa facem produsul tuturor numerelor de la $n-k+1$ la $n$, după cum reiese din simplificarea factorialelor din fracție.

# Numărul de aranjamente
Varianta iterativă:
```cpp
int aranjamente(int n, int k){
	int prod = 1;
	for(int i=n-k+1; i<=n; i++)
		prod*=i;
	return prod;
}
```
Varianta [[Recursivitatea|recursivă]]:
```cpp
int aranjamente(int n, int k){
	if(k==0)
		return 1;
	return (n-k+1) * aranjamente(n, k-1);
}
```
# Generarea aranjamentelor
Acest algoritm generează toate $A_n^k$, și are o complexitate aproximativă de $O(k\times n^k)$. La fel ca în cazul [[Permutări#Generarea permutărilor|algoritmului de generararea permutărilor]], se folosește un vector `P[ ]` pentru a verifica dacă un element a fost deja folosit, singura diferență fiind condiția de oprire care este atunci când `pas` ajunge la `k`: 
```cpp
int n, k, P[21], x[21];

void afis()
{
    for (int i = 1; i <= k; ++i)
        cout << x[i] << ' ';
    cout << "\n";
}

void back(int pas)
{
    for (int i = 1; i <= n; ++i)
        if (!P[i])
        {
            P[i] = 1;
            x[pas] = i;
            if (pas == k)
                afis();
            else
                back(pas + 1);
            P[i] = 0;
        }
}

int main()
{
    cin >> n >> k;
    back(1);
}
```

# Alte formule și explicații matematice
$A_n^k=\frac{n!}{(n-k)!}=n\times(n-1)...\times(n-k+1),\ 0\le k \le n,\ \ n,k\in \mathbb{N}$ 

$A_n^0=1$

$A_n^k=A_{n-1}^k+kA_{n-1}^{k-1}$

$A_n^k=nA_{n-1}^{k-1}$

$A_k^n=(n-k+1)A_n^k-1$

$A_n^k=\frac{n}{n-k}A_{n-1}^k$
