[[Merge Sort]] este un algoritm de [[Sortare]] care folosește ca idee de baza [[Divide et Impera]] si [[Recursivitatea]].
Ideea de la baza acestei metode este sortarea celor 2 jumătăți de secvențe și interclasarea lor. Astfel, având în vedere că lungimile secvențelor se înjumătățesc constant, numărul de pași în adâncime pe care îi va face recursivitatea este maxim $\log_2\ n$, iar toate interclasările vor duce la complexitatea finală n (dimensiunea șirului întreg). Astfel [[Merge Sort]], cât și [[Quick Sort]] au complexitate medie de $O(n\times \log_2 n)$.
Motivul pentru care [[Quick Sort]] este preferat peste [[Merge Sort]] este că [[Merge Sort]] folosește un vector auxiliar (în exemplu este folosit vectorul `c[ ]` ), deci complexitatea de spațiu este mai mare
```cpp
void mergeSort(int st, int dr){
    if(st == dr)
        return;
    else{
        int mij = (st + dr) / 2;
        mergeSort(st, mij);
        mergeSort(mij + 1, dr);
        int inda = st, indb = mij + 1, indc = 0;
        while(inda <= mij && indb <= dr){
            if(a[inda] <= a[indb])
                c[indc++] = a[inda++];
            else
                c[indc++] = a[indb++];
        }
        while(inda <= mij)
            c[indc++] = a[inda++];
        while(indb <= dr)
            c[indc++] = a[indb++];
        for(int i = 1; i <= indc; ++i)
            a[st + i - 1] = c[i];
    }
}
```