Ridicarea la putere ($a^n$) se poate face in [[Complexitatea de timp|complexitate de timp]] logaritmica $O(\log_2 n)$ folosind [[Recursivitatea|recursivitate]].

$2^{10}=2^5\times2^5$

$2^5=2^2\times2^2\times2$

$2^2=2^1\times2^1$

Ca să tratăm cazul in care exponentul este impar, când acesta trebuie înmulțit încă o dată cu baza, îi verificăm paritatea

```cpp
int alab(int a, int b){
	if(b == 0)
		return 1;
	int m = alab(a, b/2);
	if(b % 2 == 0)
		return m * m;
	else return m * m * a;
}
```