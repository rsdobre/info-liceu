# Definiție
Complexitatea timp se exprima in general sub forma $O(x)$ unde $x$ reprezintă numărul total de operații pe care programul nostru le va face. $x$ nu este exprimat niciodată ca valoare absolută ci mai mult ca și o suma de alte variabile care reprezintă datele de intrare ale programului. Exemplu: $O(n + m)$ reprezintă faptul că programul nostru va face $n + m$ pași unde $n$ si $m$ sunt date de intrare.

Vezi regulile pentru [[Notația O|notația O]].
Vezi și [[Timpul de execuție|estimarea timpului de execuție]]
# Tipuri de complexități
- $O(1)$ se numește complexitate constantă. Ea este complexitatea tuturor algoritmilor care nu conțin structuri repetitive.
- $O(\log_2n)$ se numește complexitatea logaritmică. Exemple în acest sens reprezintă algoritmul de algoritmul de [[Căutarea binară|căutare binară]] sau [[Bazele de numerație|transformarea în baza 2]].
- $O(\sqrt n)$ se numește complexitate radical. Un exemplu în acest sens este algoritmul de [[Divizibilitate|determinarea divizorilor unui număr]].
- $O(n)$ se numește complexitate liniară. Ea este cea mai de dorit complexitate când operăm pe un vector sau șir. Exemple în acest sens sunt algoritmii de [[Căutarea secvențială|căutare secvențială pe vector]] și [[Sortare prin numărare|sortarea prin numărare]].
- $O(n\times \log_2n)$ are ca exemple clasice sunt metodele de sortare eficiente [[Quick Sort]] și [[Merge Sort]], sau o [[Căutarea binară|căutare binară]] de $n$ elemente într-un vector cu $n$ elemente.
- $O(n^2)$ se numește complexitate pătratică. Ea este cea mai de dorit pentru lucrul cu [[Matrice|matrice]] (e necesară pentru citirea, afișarea și parcurgerea lor). Alte exemple le reprezintă algoritmii de sortare prin [[Sortare prin inserție|inserție]], [[Sortare prin selecție|selecție]] sau [[Metoda bulelor|bubble sort]].
- $O(n!)$ se numește complexitate factorială. Un exemplu îl reprezintă [[Permutări#Generarea permutărilor|generarea permutărilor]] sau alți algoritmi [[Backtracking|backtracking]] care generează toate mulțimile.
- $O(n^n)$ se numește complexitate exponențială. Sunt extrem de lenți, e foarte greu de calculat cu $n\gt 10$. Un exemplu în acest sens este algoritmul de [[Backtracking|backtracking]] care generează toate mulțimile de $n$. De asemenea $O(n!)$ poate fi aproximat la $O(n^n)$, iar $\ O(2^n),\ O(3^n),\ O(a^n)$ sunt și ele numite complexități exponențiale.
# Erori
“Time limit exceeded” este o eroare des întâlnita care semnifică faptul că complexitatea timp a algoritmului proiectat de noi nu este suficient de bună, motiv pentru care trebuie sa proiectăm un nou algoritm mai bun din acest punct de vedere.