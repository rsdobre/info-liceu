Expresiile se formează cu ajutorul [[Expresii#Operatori aritmetici|operatorilor aritmetici]], [[Expresii#Operatori logici|logici]], [[Expresii#Operatori relaționali|relaționali]].
# Operatori
## Operatori aritmetici
## Operatori relaționali
Operatorii relaționali evaluează anumite expresii non-binare cu `true` sau `false` pentru a putea folosi [[#Operatori logici|operatori logici]] ulterior și pentru a forma [[#Expresii logice|expresii logice]].
- $=$ (egal) este `==`
- $\neq$ (inegal) este `!=`
- $\lt$ (mai mic) este `<`
- $\leq$ (mai mic sau egal) este `<=`
- $\gt$ (mai mare) este `>`
- $\geq$ (mai mare sau egal) este `>=`
## Operatori logici
Operatorii logici înlănțuiesc o mulțime de expresii și evaluează în funcție de operator tipul expresiei (`true` sau  `false`).
- `sau` este `||` 

| P | Q | P sau Q |
| ---- | ---- | ---- |
| A | A | A |
| A | F | A |
| F | A | A |
| A | A | F |
- `și` este `&&` 

| P | Q | P și Q |
| ---- | ---- | ---- |
| A | A | A |
| A | F | F |
| F | A | F |
| F | F | F |
- negarea (sau `not`) este `!`

| P | not P |
| ---- | ---- |
| A | F |
| F | A |

**ATENȚIE** la negarea [[#Operatori relaționali|operatorilor relaționali]] deoarece `!(x<y)` este echivalent cu `x>=y` și <mark style="background: #FF5582A6;">NU</mark> `x>y`. Deci când negăm luăm complementul operației relaționale.
De pentru operatorii logici asemenea putem spune că negăm operatorul din interior împreună cu celelalte valor `!(x||y)` devine `!x && !y` ([[#Reguli de simplificare|vezi regulile de simplificare]]).
## Operatori pe biți
# Expresii logice
 La înlănțuirea mai multor expresii logice apar probleme din cauza ordinii operațiilor. Pentru a evita aceasta situații vom folosi paranteze în interiorul expresiilor
 
| Prioritate | Operator | Simbol |
| ---- | ---- | ---- |
| 1 (se execută primul) | Negația logică | `!` |
| 2 | Aritmetici multiplicativi | `* / %` |
| 3 | Aritmetici aditivi | `+ -` |
| 4 | Relaționali | `< > <= >=` |
| 5 | Și logic | `&&` |
| 6 (se execută ultimul) | Sau logic | `||` |
## Reguli de simplificare
Pentru a simplifica expresiile mai rapid putem ține cont de următoarele reguli:
- `!(x && y)` devine `!x || !y`
- `!(x || y)` devine `!x && !y`
- `!(x <= y)` devine `x > y`
- `!(x > y)` devine `x <= y`
- `!(x == y)` devine `x!=y`
- `x <= y && x >= y` devine `x==y`