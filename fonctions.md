<[back](./boucles.md) - [accueil](./README.md) - [next](./conditions.md)>

# Fonctions

Une fonction permet de définir un bout de code qui peut être utilisé plusieurs fois. Elle est introduite par le mot clé ```def```, un nom, des arguments (optionnels), le corps du code et le mot clé ```return``` (ou ```print```) pour retourner (ou pour afficher) une valeur. Le corps du code doit être *indenté* de la définition de la fonction. Plusieurs exemples de fonctions sont donnés ci-dessous. 

```
def f(prenom):
  message = f'Hello {name}!'
  print(message)

>>> f("Morgane")
Hello Morgane !
```

```
def fct(x,y):
  return 3*x+y

>>> fct(2,3)
9
```

```
def affiche(chaine):
  for i in range(len(chaine)):
    print(f'i = {i}')
    print(chaine[i])

>>> s = "top"
>>> affiche(s)
i = 0
t
i = 1
o
i = 2
p
```

**À ton tour !** Soit une liste d'entiers de ton choix. Code une fonction qui calcule la somme des entiers de cette liste en utilisant une boucle ```for i in range()```. 
<details>
  <summary>Solution</summary>
 
```
def somme(liste):
  somme = 0
  for i in range(len(liste)):
    somme = somme + liste[i]
  return somme

>>> L = [2,33,50,26]
>>> somme(L)
111
```

</details>

<[back](./boucles.md) - [accueil](./README.md) - [next](./conditions.md)>

