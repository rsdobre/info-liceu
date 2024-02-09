Coada este o structură de date care respecta regula că primul element introdus sa fie primul extras, deci
- FIFO = First In First Out
Mereu primul element introdus este primul extras. Ea funcționează ca o coadă reală: Primul venit > Primul servit
![[Pasted image 20240202231027.png|800]]
Funcțiile unei cozi sunt: Push, Pop, Front și Empty:
```cpp
int Q[1001], st = 1, dr = 0;

bool empty(){
    return st > dr;
}
int front(){
    if (!empty()){
        return Q[st];
    }
}
void push(int val){
    Q[++dr] = val;
}

void pop(){
    if (!empty()){
        st++;
    }
}
```
- empty - verifica daca o stiva este goală
- top - returnează elementul din fata cozii
- push - adaugă un element la coadă
- pop - elimina elementul din fata cozii