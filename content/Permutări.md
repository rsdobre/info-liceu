$P_n=n!$
Permutările lui n sunt chiar factorial de n, deci implementăm o funcție de factorial
# Numărul de permutări
Cea mai ușor de implementat e varianta [[Recursivitate|recursivă]]:
```cpp
int permutari(int n){
	if(n <= 1)
		return 1;
	return n * permutari(n-1);
}
```

Varianta iterativă:
```cpp
int permutari(int n){
    int prod = 1;
    for(int i = 2; i <= n; ++i)
        prod *= i;
    return prod;
}
```
# Generarea permutărilor
Generarea tuturor permutărilor se face folosind [[Backtracking]], și are complexitate de timp $O(n\times n!)$. Pentru a ține cont de elementele deja folosite, utilizăm un vector de apariție, `P[ ]`, și verificăm daca elementul pe care dorim sa îl utilizăm a mai fost folosit deja:
```cpp
int n; // elementele vor fi 1, 2, 3, ..., n -> n este in limita a 10 elemente
int x[11], P[11];

void afis(){
    for(int i = 1; i <= n; ++i)
        cout << x[i] << ' ';
    cout << "\n";
}

void back(int pas){ // complexitate: n * n!
    for(int i = 1; i <= n; ++i)
        if(!P[i]){
            P[i] = 1;
            x[pas] = i;
            if(pas == n)
                afis();
            else 
	            back(pas + 1);
            P[i] = 0;
        }
}
int main(){
	cin >> n;
	back(1);
}
```
# Cum gândești grilele de la BAC
- Permutarea mulțimii {1, 2, 3, 4}:
	- Inițial, pornim de la 1,2,3,4
	- Pe ultima poziție, nu mai putem pune o valoare mai mare, așa că modificăm penultima valoare de la 3, la 4 și obținem permutarea 1,2,4,3
	- Pe penultima valoare nu mai putem modifica valoarea, așa că pe antepenultima o facem 3 si rezulta șirul 1,3,2,4. Acum putem din nou să modificam penultima valoare in 4 si avem permutarea 1,3,4,2
	- ETC
- După acest procedeu putem să facem și backtracking pe cuvinte, ca la BAC, doar atribuim cuvintelor valori numerice
# Alte formule și precizări matematica

$P_0=1$