Metoda Greedy este o metoda folosită in algoritmică care presupune ca la fiecare posibilitate de a alege o continuare, să se aleagă metoda cea mai favorabil la acel moment. Greedy = lacom. 

Metoda Greedy este o metoda foarte generala care nu duce mereu la un rezultat final corect, dar exista și multe probleme care se rezolvă correct prin această metoda. Decizia de a putea folosii acest concept sta in mâinile programatorului.

Ea astfel e mai mult un concept decât un algoritm propriu-zis, deci nu există un șablon, ca la [[Backtracking]], unde aveam un algoritm de bază care putea fi modificat pentru orice problemă. 

În general, se citește problema și se încearcă o rezolvare in cap a acesteia. Dacă se ajunge la rezultatul final correct prin raționamentul uman, abordarea a fost una bună si vom încerca punerea in cod a acestuia. Pentru a ajunge la o soluție corectă, cel mai ușor este să luăm exemple, chiar dacă nu sunt date, ca în cazul grilei [[Submulțimea cu intervale care nu se intersectează]]

Un exemplu mai uman în care poate fii folosită [[Metoda Greedy]] este căutarea unei oaze în deșert. La fiecare pas pe care îl fac trebuie să decid în ce direcție mă îndrept. Dacă am de ales între a urca pe dune de nisip sau a merge pe teren plat, voi alege terenul plat, chiar dacă nu știu că oaza se află acolo. Totuși există posibilitatea ca oaza să se afle chiar după duna de nisip.

Deci ca reguli generale:
- Problemele cu [[Metoda Greedy]] sunt naturale, presupun niște raționamente umane
- La fiecare pas, fac o decizie, care este cea mai favorabilă în acel moment
- Decizia este luată pe baza unui minim local
- Deși poate fi folosită în rezolvarea oricărei probleme, în majoritatea cazurilor nu ne va duce la un rezultat corect, dar există multe probleme unde aceasta ne va duce la un răspuns corect. Deci noi ca programatori trebuie să decidem dacă metoda corectă de a aborda problema prin [[Metoda Greedy]].
# Exemple
Un exemplu simplu care demonstrează [[Metoda Greedy]] este problema [[Masini]]

În admiterea de la UBB se dau cam 1-2 grile de [[Metoda Greedy]]