Tradus divide și stăpânește, presupune sa împarți o problema in cat mai multe bucăți mai mici de obicei prin [[Recursivitate]], dar uneori și iterativ, cum se mai practică pentru [[Căutare binară]]. În cazul programării, se folosește mai ales pentru vectori sau șiruri, de ex [[Merge Sort]]. Trebuie menționat că deși în cazul [[Merge Sort]] complexitatea este de $O(n\times log_{2} (n))$, asta nu este o caracteristica a [[Divide et Impera]], suma vectorilor având complexitate $O(n)$.

Un exemplu pentru suma vectorilor este
```cpp
int sum_vector(int a[], int st, int dr){
	if(st==dr)
		return a[st];
	int mij = (st + dr)/2;
	return sum_vector(a, st, mij) + sum_vector(a, mij+1, dr);
}
```

Cele mai rapide sortări, [[Merge Sort]] si [[Quick Sort]]  folosesc [[Divide et Impera]] pentru a ajunge la o complexitate de $O(n\times log_{2} (n))$