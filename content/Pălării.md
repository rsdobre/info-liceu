---
tags:
  - "#grile"
  - UBB
---
# Enunț
![[Pasted image 20240208210258.png|800]]
# Explicație
Ca să rezolvăm corect problemă trebuie să ne punem în poziția celor 3 participanți. Așadar:
- A vede ce pălării au B și C
- B aude dacă A știe ce pălărie are pe cap și vede pălăria lui C
- C aude dacă A și B știu
Culoarea pălăriei lui A este cea mai puțin importantă deoarece nimeni nu știe nimic despre ea (cu excepția primului singur caz enunțat mai jos).
Așa ca putem începe exclude cazuri:
- Dacă B și C ar avea pălării albe, **A ar știi că are pălărie roșie** <mark style="background: #FF5582A6;">NU CONVINE</mark>
- Dacă B ar avea pălărie roșie iar C pălărie albă: îl vede pe C cu pălăria albă și aude că A nu știe, clar pălăria lui nu are cum să fie tot albă(altfel A ar știi), deci **B ar știi că are pălărie roșie** <mark style="background: #FF5582A6;">NU CONVINE</mark>
- Dacă B ar avea pălărie albă și C pălărie roșie sau și B și C au pălării roșii: îl vede pe C cu pălăria roșie și aude că A nu știe, deci nu poate fii sigur ce pălărie are el. <mark style="background: #BBFABBA6;">CONVINE</mark>
Practic singurele posibilități de aranjare a pălăriilor sunt
- A alb, B roșu, C roșu
- A roșu, B roșu, C roșu
- A alb, B alb, C roșu
- A roșu, B alb, C roșu
# Răspunsuri
Așa că variantele de răspuns:
A. C nu are niciodată pălărie albă - <mark style="background: #FF5582A6;">este întotdeauna FALSĂ</mark>
B. B poate avea uneori pălărie roșie - <mark style="background: #BBFABBA6;">este uneori ADEVĂRATĂ</mark>
C. A și B pot avea pălării de culori diferite - <mark style="background: #BBFABBA6;">este uneori ADEVĂRATĂ</mark>
D. C are întotdeauna pălărie roșie - <mark style="background: #BBFABBA6;">este întotdeauna ADEVĂRATĂ</mark>