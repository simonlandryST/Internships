<[back](./README.md) - [accueil](./README.md) - [next](./affichage.md)>

# Prérequis Mathématiques

## Bases
* Base 10 : système décimal 0, 1, 2, 3, ..., 9, 10. 
* Base 2 : système binaire basé sur des bits, 0 et 1. Pour écrire un nombre, on compte en puissances de 2 de droite à gauche.
  * Par exemple, $10 = 2^3 + 2^2$, $8 = 2^3$, $3 = 2^2 + 2^0$. L'écriture binaire en 4 bits de 10 est 1100, celle de 8 est 1000 et celle de 3 est 0011.
* Base 16 : système hexadécimal basé sur les 16 caractères : 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E et F. Les lettres peuvent s'écrire en minuscules. Pour écrire un nombre, on compte en puissances de 16, de droite à gauche.
  * Par exemple, $1237 = 4 × 16^2 + 13 × 16^1 + 5 × 16^0$. L'écriture hexadécimale de 1237 est 4D5.

Pour indiquer la base souhaitée dans du code python, il faut utiliser un préfixe :

* Base 10 : rien devant
* Base 2 : ```0b```
* Base 16 : ```0x```

**À ton tour !** Utilise la console pour voir les valeurs des nombres suivants : ```0b10101010, 0xaa, 0xAA, 170```
<details>
  <summary>Solution</summary>
 
```
>>> 0b10101010
170
>>> 0xaa
170
>>> 0xAA
170
>>> 170
170
```
</details>

## Calculs arithmétiques

On peut coder les différentes opération mathématiques :

* Addition : 1+1
* Soustraction : 2-1
* Multiplication : 3*4
* Puissance : 3**2
* Division simple : 5/2
* Division entière : 5//2
* Modulo : le résultat de a%b est le reste de la division euclidienne de a par b. 

 **À ton tour !** Calcule la moyenne de 127, 45 et 72.6.

<details>
  <summary>Solution</summary>

```
>>> (127+45+72.6)/3
81.5333333333
>>> (127+45+72.6)//3
81.0
```

 </details>

 **À ton tour !** Calcule les modulos suivants : 12%2, 16%3, 30%4, 43%4, 30%26, 5%2

 <details>
  <summary>Solution</summary>

```
>>> 12%2
0 
>>> 16%3
1 
>>> 30%4
2 
>>> 43%4
3 
>>>
30%26
4 
>>> 5%2
5 
```
* 12 = 2*6 + 0
* 16 = 3*5 + 1
* 30 = 4*7 + 2
* 43 = 4*10 + 3
* 30 = 26*1 + 4
* 5 = 2*0 + 5

 </details>

 <[back](./README.md) - [accueil](./README.md) - [next](./affichage.md)>
