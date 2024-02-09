Sunt necesare pentru [[Programa de admitere UBB 2024|admiterea de la UBB]] doar [[#Interschimbare clasică (metoda paharelor)|interschimbarea clasică]], [[#Interschimbare prin adunare|prin adunare]], [[#Interschimbare prin scădere|prin scădere]] și [[#Interschimbare prin înmulțire|prin scădere]].
# Interschimbare prin funcții predefinite 
```cpp
swap(x,y);
```
# Interschimbare clasică (metoda paharelor)
În această metodă se folosește o variabilă auxiliară (încă un pahar).
```cpp
void swap(int &x, int &y){
	int aux=x;
	x=y;
	y=aux;
}
```
# Interschimbare prin adunare
```cpp
void swap(int &x, int &y){
	x=x+y;
	y=x-y;
	x=x-y
}
```
## Forma contrasă
```cpp
void swap(int &x, int &y){
	x+=y;
	y=x-y;
	x-=y;
}
```
# Interschimbare prin scădere
```cpp
void swap(int &x, int &y){
	x=x-y;
	y=x+y;
	x=y-x;
}
```
## Forma contrasă
```cpp
void swap(int &x, int &y){
	x-=y;
	y+=x;
	x=y-x;
}
```
# Interschimbare prin înmulțire
```cpp
void swap(int &x, int &y){
	x=x*y;
	y=x/y;
	x=x/y;
}
```
## Forma contrasă
```cpp
void swap(int &x, int &y){
	x*=y;
	y=x/y;
	x/=y;
}
```
# Interschimbare pe biți (XOR)
Nu intră la [[Programa de admitere UBB 2024|admiterea de la UBB]]
```cpp
void swap(int &x, int &y){
	x=x^y;
	y=x^y;
	x=x^y;
}
```
# Interschimbare prin împărțire
Această variantă deși pare corectă matematic, ea nu funcționează în C++ deoarece împărțirea pe `int` returnează doar câtul, iar pe `float` nu ar funcționa din cauza rotunjirilor. Teoretic ar putea funcționa în pseudocod, deoarece ar fi evaluată matematic, și simplificările ar fi corecte. dar nu a fost folosită niciodată in [[Programa de admitere UBB 2024|admiterea de la UBB]]. Așadar, această variantă de interschimbare este <mark style="background: #FF5582A6;">GREȘITĂ</mark>
```cpp
void swap(int &x, int &y){
	x=x/y;
	y=x*y;
	x=y/x;
}
```
## Forma contrasă
```cpp
void swap(int &x, int &y){
	x/=y;
	y*=x;
	x=y/x;
}
```