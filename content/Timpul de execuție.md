Procesoarele moderne au o capacitate teoretică de $10^9$ operații/secundă. În majoritatea cazurilor ni se cere să facem algoritmi care au timp de execuție sub $0.1$ secunde, deci procesorul ar putea face maxim $10^8$ pași. 
# Operație
În cazul estimării timpului de execuție, o operație reprezintă cea mai mică modificare sau evaluare. De exemplu: `i++` , fiecare condiție independentă dintr-un `if()`. Cu alte cuvinte, o operație este orice expresie care trebuie evaluată.

În cazul unui `for` cu $10^6$ pași, el va face undeva pe la $10^7$ operații (incrementare, comparații, și toate operațiile liniare din interior pe care noi le-am redus la $O(1)$ în calculul [[Complexitatea de timp|complexității de timp]]).
# Estimarea timpului de execuție
Astfel, după ce am calculat [[Complexitatea de timp|complexitatea de timp]], următorul pas este să înlocuim variabilele din [[Notația O|expresia]] complexității cu maximul valorilor posibile pentru fiecare și să vedem cât e rezultatul. Dacă rezultatul depășește $5\times 10^6$, algoritmul este prea lent. Deși pare radical considerând că în general avem $10^8$ pași, trebuie să luăm în considerare toate [[#Operație|operațiile]] pe care noi le-am redus din calculul complexității de timp.
# Complexitatea potrivită
Pentru date până în 2000 putem considera o [[Complexitatea de timp|complexitate pătratică]] $O(n^2)$. 
În cazul datelor mai mari, încercăm $O(n)$, dacă nu putem, încercăm $O(n\times \log_2n)$. Dacă nici așa nu merge, trebuie să meargă $O(n\times \sqrt n)$.
În general sunt 2 metode de rezolvare eficientă a unei probleme:
1. Scriem un program, îl analizăm, iar dacă timpul de execuție depășește timpul cerut încercăm să găsim o variantă mai eficientă
2. Analizăm datele de intrare și cerința și încercăm să determinăm care ar fi cea mai bună complexitate posibilă. Apoi căutăm algoritmii care să ne ducă la acea complexitate.
## Exemplu
Ni se dau 2 vectori de $n$ elemente sortate și ni se cere găsirea elementelor comune.
- Dacă $n\leq 10^3$ am putea efectua o [[Căutarea secvențială|căutare secvențială]] pentru fiecare element dintr-un vector în altul, și am face $n$ căutări cu o complexitate de $O(n)$, deci am avea o complexitate $O(n^2)$, care s-ar încadra în numărul de pași ($(10^3)^2=10^6\lt 5\times 10^6$)
- Dar dacă $n\leq 10^5$ este evident că am depăși cu mult numărul de pași și timpul de execuție. Așa că am putea efectua [[Căutarea binară|căutări binare]] între elementele din vectori. Deci am avea $n$ căutări cu o complexitate de $O(\log_2 n)$, rezultând o complexitate finală de $O(n\times \log_2 n)$ care s-ar încadra în numărul de pași (nu chiar, dar aproximativ)
- Mai eficient de atât putem considera metode folosind [[Interclasarea|interclasarea]] sau vectori de frecvență.