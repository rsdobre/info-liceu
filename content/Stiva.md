Stiva (Stack in engleza) este o structură de date care respectă regula că primul element introdus să fie ultimul extras după regula
- FILO = First In Last Out
Deci mereu ultimul element introdus este primul scos
![[Pasted image 20240202225630.png|400]]
Funcțiile unei stive sunt Push, Pop, Top, și Empty
```cpp
int S[1001];
int st = 1, dr = 0;

bool empty(){
    return st > dr;
}
int top(){
    if (!empty()){
        return S[dr];
    }
}
void pop(){
    if (!empty()){
        dr--;
    }
}
void push(int val){
    S[++dr] = val;
}
```
Astfel funcțiile au următoarele roluri
- empty - verifică daca o stivă este goala
- top - returnează ultimul element (cel la care avem acces) din stivă
- pop - șterge ultimul element din stivă
- push - adaugă un element in stivă pe ultima poziție