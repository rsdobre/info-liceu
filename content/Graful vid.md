Dacă eliminăm toate nodurile/vârfurile dintr-un [[Grafuri|graf]] am obține **graful vid** $G=(\varnothing, \varnothing)$.

Există niște polemici în legătură cu graful vid, existența lui și dacă este un [[Grafuri#Subgraf|subgraf]], deoarece graful este definit ca având mulțimea nodurilor nevidă. Pe [Wikipedia](https://ro.wikipedia.org/wiki/Graf) se menționează că mulțimea nodurilor este nevidă, dar se definește graful vid.

Fie $V$ mulțimea nodurilor unui graf
Dacă acceptăm că graful vid există, $\varnothing\subset V$, ar trebui să îl includem în calculul subgrafurilor, dar și $V\subset V$, deci nu am mai avea numărul de subgrafuri $2^n-1$

Cert este că formula numărului de subgrafuri rămâne aceeași, deoarece unii numără graful vid ca subgraf dar nu numără graful inițial(Paul în curs), iar alții numără graful inițial dar afirmă că graful vid nu există([pbinfo](https://www.pbinfo.ro/?pagina=articole&subpagina=afisare&id=810#intlink-6)).

Oricum ar fi, cu $n$ nr de moduri:

$C_n^1+C_n^2+...+C_n^n=2^n-1$

$C_n^0+C_n^1+...+C_n^{n-1}=2^n-1$
