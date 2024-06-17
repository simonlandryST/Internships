<[back](./fonctions.md) - [accueil](./README.md)>

# Exercice 1 

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

# Exercice 2 

Soit la fonction ```exercice2(str)``` avec ```str``` une chaîne de caractère.

Q1. Parcourir les éléments de la chaîne de caractères str. Si deux éléments consécutifs sont les mêmes, les changer tous les deux par la lettre "e". 

Q2. Décaler toutes les lettres "c" de 3 positions dans l'alphabet. 

Q3. Tester la fonction sur la chaîne "chiffrement du message securite".

# Exercice 3

En python, il est possible de tester le résultat d'une fonction. Par exemple ```if somme(3,4) == 7:``` teste si le résultat de la fonction ```somme(3,4)``` est égale à 7

Soit la chaîne de caractère "je chiffre mon message". On va faire un chiffrement symétrique de la manière suivante

Q1. Ajouter dans votre code la fonction suivante. Elle permet de trouver la l'index d'une lettre dans l'alphabet français. Par exemple, la lettre i dans "simon" est à l'index 1 dans le mot "simon" et à l'index 8 dans l'alphabet (c'est la 9e lettre de l'alphabet).

```
alphabet = "abcdefghijklmnopqrstuvwxyz
def position_alphabet(letter):
    return alphabet.find(letter)

>>> print(position_alphabet("c")
2
```


 # Autres cours

* [Prérequis mathématiques](./prerequismaths.md)
* [Affichage](./affichage.md)
* [Type de Données](./typededonnees.md)
* [Variables](./variables.md)
* [Fonctions](./fonctions.md)
* [Conditions](./conditions/md)

<[back](./fonctions.md) - [accueil](./README.md)>
