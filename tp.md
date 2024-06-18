# Lundi 

## Exercice 1 

Soit la fonction ```exercice1(L)``` avec la liste L en paramètre. 

Q1. Changer tous les 5 en 10. Il faut parcourir les éléments de la liste L, si un élément est égal à 5, on le change en 10.

Q2. Soit la variable S = 0. Calculer la somme des 4 premiers éléments de la liste L et stocker le résultat dans la variable S.

Q3. Ajouter le mot "ajout" après chaque 10 de la liste L. Il faut parcourir les élements de la liste L, si un élément est égal à 10, il faut ajouter le mot "ajout" après cet élément. 

Q4. Retourner la liste L et l'entier S.

Q5. Tester la fonction sur la liste [5,78,92,100,5,67,5]

<details>
  <summary>Solution</summary>
  
```
def exercice1(L):
  # Q1
  for i in range(len(L)):
    if L[i] == 5:
      L[i] = 10
  # Q2
  S = 0
  for i in range(4):
    S = S + L[i]
  # Q3
  for i in range(len(L)):
    if L[i] == 10:
      L.insert(i+1,"ajout")
  # Q4
  return L,S

>>> ma_liste = [5,78,92,100,5,67,5]
>>> print(exercice1(ma_liste))
[10,"ajout",78,92,100,10,"ajout",67,10,"ajout"], 280
```

</details>

## Exercice 2 

Soit la fonction ```exercice2(str)``` avec ```str``` une chaîne de caractère.

Q1. Parcourir les éléments de la chaîne de caractères str. Si deux éléments consécutifs sont les mêmes, les changer tous les deux par la lettre "e". 

Q2. Décaler toutes les lettres "c" de 3 positions dans l'alphabet. 

Q3. Tester la fonction sur la chaîne "chiffrement du message securite".

# Mardi 

## Rappel sur les fonctions

On définit une fonction de cette manière : 

```
def nom_fonction(parametres):
  ...corps de la fonction...
  ...en utilisant les parametres...
  return resultat
```

On fait appel à la fonction par : 

```
print(nom_fonction(mes_parametres)
```

Par exemple, la fonction suivante calcule la somme entre l'élément a et l'élément b. 

```
def somme(a,b):
  return a+b

>>> print(somme(6,8))
14
```
## Exercice 1 - à la main

Q1. Ecrire sur une feuille le mot "cryptologie". Reproduire le tableau suivant :

|A|B|C|D|E|F|G|H|I|J|K|L|M|N|O|P|Q|R|S|T|U|V|W|X|Y|Z|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|24|25|26|
| | | | | | | | | | | | | | | | | | | | | | | | | | |

Q2. Ecrivez les positions dans l'alphabet des lettres du mot "cryptologie" et ajouter 4 à ces positions. Par exemple, pour la première lettre on a :

C -> position 2 -> +4 = position 6 -> C devient G

Q3. Que donne le chiffrement symétrique du mot "cryptologie" avec la clé secrète 4 ?

Q4. Détaillez les différentes étapes de réflexion. En premier on fait quoi, puis en deuxième, etc. 

Q5. Déchiffrer à la main le mot chiffré obtenu en Q3. Comment faut-il procéder ? 

## Exercice 2 - à la main et avec python

La fonction suivante permet de trouver l'index d'une lettre dans l'alphabet français. Par exemple, la lettre i dans "tim" est à l'index 1 dans le mot "tim" et à l'index 8 dans l'alphabet (c'est la 9e lettre de l'alphabet).

```
alphabet = "abcdefghijklmnopqrstuvwxyz"
def position_alphabet(letter):
    return alphabet.find(letter)

>>> print(position_alphabet("c")
2
```

Q1. Quel est l'index de la lettre "r" dans la chaîne de caractère S = "cryptologie" ? Manuellement et en python.

Q2. Quelle est la position de la lettre "r" dans l'alphabet français ? Manuellement et en python. 

Q3. On veut décaler la lettre "r" de 2 positions dans l'alphabet sans utiliser la manipulation ```S[:i]+"t"+S[i+1:]```. Comment peut-on faire (en python) ? 

## Exercice 3

Soit ```elt``` un élément de la chaîne de caractère. La commande ```elt.isalpha()``` retourne ```True``` si elt est une lettre et retourne ```False``` si ce n'est pas le cas (par exemple un espace ou un chiffre).

Soit les chaînes de caractères suivantes :
* S = "on veut chiffrer le mot securite"
* alphabet = "abcdefghijklmnopqrstuvwxyz"

Ecrire une boucle qui parcours les éléments de la string S. Tester si chaque élément est une lettre. Si oui, décalez cette lettre de 3 positions vers la droite en utilisant la variable ```alphabet```. Sinon, ne faites rien (il suffit de ne pas mettre de boucle ```else:```). Retourner S. 

Vous venez de coder une fonction de chiffrement symétrique de César. 

## Exercice 4

Trouver d'autre(s) manière(s) de coder un chiffrement de César sur la phrase de votre choix. On peut par exemple passer en paramètres :

* Le message à chiffrer et la clé secrète
* Le message à chiffrer et une chaîne de caractère

## Exercice 5 - Attaques à la main

Q1. Comptez la fréqence de chaque lettre de votre message chiffré. 

Q2. Comparez ces fréquences à celles des lettres de l'alphabet français et associer les lettres du messages chiffré à une lettre possible de l'alphabet.

Q3. Tentez de déchiffrer votre message chiffré. 

Q4. Quelles conclusions faites-vous ?

## Exercice 6

Rendez-vous [ici](https://github.com/simonlandryST/Internships/tree/main?tab=readme-ov-file#point-de-d%C3%A9part) dans la partie "Point de départ". 










