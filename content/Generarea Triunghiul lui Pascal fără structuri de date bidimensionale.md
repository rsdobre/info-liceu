#UBB 
![[Pasted image 20240205195107.png|700]]
Problemă asta implică utilizarea unui [[Vectori|vector]] care să fie suprascris pe măsură ce se parcurg liniile. Aceasta este aproape aceeași metodă ca [[Triunghiul lui Pascal#Varianta cu un singur Vectori vector|varianta de generare cu un singur vector a triunghiului lui Pascal]], doar că se va afișa toată linia.
# Rezolvare
## Varianta optimă
Citim `r`, îl introducem în funcția `pascal()`, iar apoi afișăm toate valorile din vectorul generat.
```cpp
#include <iostream>
using namespace std;
void pascal(int niv, int c[]){
    int level = 1;
    c[1] = c[2] = 1;
    while(level < niv){
        level++;
        c[level + 1] = 1;
        for(int i = level; i >= 2; i--)
            c[i] += c[i-1];
    }
}
int main(){
    int c[1001], r;
    cin >> r;
    pascal(r, c);
    for(int i=1; i<=r+1; i++)
	    cout << c[i] << " ";
    return 0;
}
```
## Varianta ineficientă
Desigur putem să rezolvăm problema mai literal, deoarece știm că valorile numerelor din [[Triunghiul lui Pascal|triunghiul lui Pascal]] reprezintă $C_\text{linie}^\text{poziție}$, `linie` și `poziție` începând de la 0.

```cpp
#include <iostream>
int combinari(int n, int k){
    if(k == 0 || n == k)
        return 1;
    return combinari(n-1, k) + combinari(n-1, k-1);
}
int main(){
	int r, c[1001];
	cin >> r;
	for(int i=0; i<=r; i++){
		c[i]=combinari(r,i);
		cout << c[i] << " ";
	}
}
```
Această variantă mai mult ca sigur nu ar fi luat punctaj maxim, deoarece este foarte [[Complexitate de timp|ineficientă]], și ar lua limită de timp.
