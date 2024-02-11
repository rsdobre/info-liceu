Fiecare tip de date este scris pe un anumit număr de [[Codul Binar#Byte|octeți]] (bytes, o grupare de 8 [[Codul binar#Bit|biți]]), iar acest număr de octeți impune o limită. Fiind stocate în memorie în [[Codul Binar|cod binar]] dimensiunile sunt direct influențate de numărul de cifre în baza 2 din reprezentarea acestora.
# Tipuri
## Numerice
### Naturale
În cazul numerelor naturale $\mathbb N$, declararea variabilei trebuie să fie precedată de `unsigned` pentru a semnala compilatorului că numărul nu are semn.
- `unsigned short` folosește 2 bytes și ia valori din: $[0, 2^{16} - 1]$
- `unsigned int` folosește 4 bytes și ia valori din: $[0, 2^{32} - 1]$
- `unsigned long long` folosește 8 bytes și ia valori din: $[0, 2^{64} - 1]$
De asemenea putem declara `unsigned x;` care este echivalent cu `unsigned int x;`
### Întregi
În cazul numerelor întregi $\mathbb Z$, declararea variabilei poate fi precedată opțional de `signed` pentru a semnala compilatorului că numărul nu are semn. Dacă nu se specifică `signed` sau `unsigned` compilatorul presupune că avem valori `signed`. Primul bit este rezervat pentru semn.
- `short` folosește 2 bytes și ia valori din: $[-2^{15}, 2^{15} - 1]$
- `int`  folosește 4 bytes și ia valori din: $[-2^{31}, 2^{31} - 1]$
- `long long` folosește 8 bytes și ia valori din: $[-2^{63}, 2^{63} - 1]$
### Raționale/Reale
Practic pot fi stocate doar numere raționale $\mathbb Q$, iar pentru numerele reale $\mathbb R \setminus \mathbb Q$ se stochează doar aproximările raționale.
- `float` folosește 4 bytes
- `double` folosește 8 bytes
## Boolean
Tipul `bool` stochează doar `1` și `0` (sau `true` respectiv `false`). Deși el stochează o valoare binară, care poate fi teoretic reprezentată printr-un bit, el folosește 1 byte (8 biți) pentru că nu avem acces ca programatori la biți, doar la bytes.
- `bool` folosește 1 byte
## Caracter
- `char` folosește 1 byte (din cauza [[Codul ASCII|codului ASCII]])
# Stocarea numerelor întregi
Luăm ca exemplu tipul de date `int`, care are [[Codul Binar#Byte|4 bytes]], deci [[Codul Binar#Bit|32 de biți]]. În acest caz, scrierea numărului trebuie să se încadreze în limita a [[Codul Binar#Bit|32 de biți]]
$2^{32} = 1\underbrace{00\ldots0}_{32\text{ de 0}}\ _{(2)}$ folosește 33 de biți, iar $2^{32} -1 = \underbrace{11\ldots1}_{32\text{ de 1}}\ _{(2)}$ ([[Codul Binar|vezi mai multe explicații]])
## `unsigned`
Cea mai mare valoare este $2^{32} -1 = \underbrace{11\ldots1}_{32\text{ de 1}}\ _{(2)}$.
![[Pasted image 20240210223244.png]]
## `signed`
Pentru reprezentarea numerelor cu semn, se va folosi un bit dintre cei alocați scrierii numărului pentru a reprezenta semnul. `1` semnifica negativ si `0` semnifica pozitiv, iar având în vedere că am folosit un bit, vor rămâne cu 1 bit mai puțin pentru reprezentarea valorilor. Din acest motiv, vom vedea ca atunci cand reprezentam numerele `signed` valorile sunt mai mici.
![[Pasted image 20240210223525.png]]
Având in vedere ca "blocăm" bitul 31 al reprezentării, ne rămân 31 de biți pentru valoarea efectivă. Din acest motiv, folosind doar 31 de biti, cea mai mare valoare pozitivă care se poate retine pe acest tip de date este $2^{31}-1$. Din acest punct de vedere, în domeniul numerelor negative *ar trebui* sa avem cel mai mic număr egal cu $-2^{31} + 1$. Dar deoarece $0$ este considerat valoare pozitivă, nu îl mai reprezentăm și ca număr negativ, deci putem memora o valoare în plus la numere negative. Deci cea mai mică valoare care poate fi memorată pentru `signed int` este $-2^{31}$.
- Este important de precizat că deși `unsigned` întotdeauna poate stoca o valoare mai mare decât `signed` (evident comparând `int` cu `int`, `short` cu `short`, etc), intervalul (sau numărul) de numere care pot fi stocate are aceeași lungime.