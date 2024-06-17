<[back](./fonctions.md) - [accueil](./README.md)>

# Exercice 1 

Soit la fonction ```exercice1(L)```. 

Q1. Changer tous les 5 en 10. Il faut parcourir les éléments de la liste, si un élément est égal à 5, on le change en 10.

Q2. Soit la variable S = 0. Calculer la somme des 4 premiers éléments et stocker le résultat dans la variable S.

Q3. Ajouter le mot "ajout" après chaque 10 de la liste. Il faut parcourir les élements de la liste, si un élément est égal à 10, il faut ajouter le mot "ajout" après cet élément. 

Q4. Retourner L et S.

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
```

</details>

 # Autres cours

* [Prérequis mathématiques](./prerequismaths.md)
* [Affichage](./affichage.md)
* [Type de Données](./typededonnees.md)
* [Variables](./variables.md)
* [Fonctions](./fonctions.md)
* [Conditions](./conditions/md)

<[back](./fonctions.md) - [accueil](./README.md)>
