# Sujet de stage : étude de la résistance d'un algorithme de chiffrement symétrique contre la cryptanalyse

## Organisation du stage

|   Durée       |   Contenu |   Compétences acquises
|---            |---        |--- 
| Lundi am | Présentation cryptologie dans les puces Présentation du stage | Comprendre l'environnement de travail Notions de cryptologie | 
| Lundi pm - mardi am | Support python, papier/ordi, premier chiffrement symétrique (César) et tests | Bases en python, réflexion mathématique et algorithmique
| Mardi pm - jeudi pm | Réflexion contre-mesures, codes python et tests | Réflexion sur un sujet en cryptographie Autonomie
| Vendredi | Conclusion, présentation des résultats | Restitution des connaissances |

## Travailler avec Python

Lancer un interpréteur _python_ :
* Installer [Spyder](https://www.spyder-ide.org/)
* Sinon, lancer une console dans le navigateur : [console](https://pyodide.org/en/stable/console.html)

## Cours

* [Prérequis mathématiques](./prerequismaths.md)
* [Affichage](./affichage.md)
* [Type de données](./typedonees.md)


 ### Variables

Une variable est utilisée pour donner un nom à un type de donnée : une string, une liste, un dictionnaire, une valeur. Par exemple, quand on définit la liste ```L = [1,2,3]```, L est une variable de type list. 

* Une variable est constituée d'un caractère entre a et z en minuscules ou majuscules.
* Une variable est reconnue partout dans le code. Par exemple, si on définit ```V = 30```, partout V vaudra 30 (sauf si la variable V est modifiée quelque part dans le code).
* Une même variable peut être ré-utilisée pour définir des types de donnée différents. Par exemple, ```V = 30``` au début puis ```V = "Hello"``` plus tard.

**À ton tour !** Quel est le résultat de la variable ```result``` tel que :

```
>>> ABC = 25
>>> result = ABC*3
>>> result
```
<details>
  <summary>Solution</summary>
 
75

 </details>

 **À ton tour !** Soit le dictionnaire suivant : 

```
dict = {'invites'         : ["Thomas","Ibrahima","Yanis","Morgane"],
        'prixparpersonne' : 120
       }
```

Q1/ Quel est le nombre d'invités ? 

<details>
  <summary>Solution</summary>
 
```
>>> dict = {'invites'         : ["Thomas","Ibrahima","Yanis","Morgane"],
            'prixparpersonne' : 120
           }
>>> n = len(dict['invites'])
>>> n
4
```

 </details>
 
Q2/ Quel est le prix d'une nuit ? 

<details>
  <summary>Solution</summary>
 
```
>>> p = dict['prixparpersonne']
>>> p
120
```

 </details>
 
Q3/ Quel est le prix total ? 

<details>
  <summary>Solution</summary>
 
```
>>> n*p
>>> 480
```

 </details>

 ### Boucles

 La boucle ```for``` permet de parcourir des éléments d'un type de donnée : 

 * Parcourir les caractères d'une string : ```for char in "Arya Stark": print(char)```
<details>
  <summary>Résultat</summary>
 
```
>>> for char in "Arya Stark": print(char)
A
r
y
a

S
t
a
r
k
```

 </details>

* Parcourir les éléments d'une liste : ```for i in [1,2,3,"go"]: print(i)```
<details>
  <summary>Résultat</summary>
 
```
>>> for i in [1,2,3,"go"]: print i
1
2
3
"go"
```

</details>

* Parcourir les clés d'un dictionnaire : ```for key in {'prenom':'Raphaelle','taille':172}: print(key)```
<details>
  <summary>Résultat</summary>
 
```
>>> for key in {'name':'Raphaelle','taille':172}: print key
prenom
taille
```

</details>

* Parcourir les valeurs d'un dictionnaire : ```for value in {'prenom':'Raphaelle','taille':172}.values(): print(value)```
 <details>
  <summary>Résultat</summary>
 
```
>>> for value in {'prenom':'Raphaelle','taille':172}.values(): print(value)
Raphaelle
172
```

</details>

**À ton tour !** Soit une string ```s = "anniversaire"```. Parcours les éléments de la liste s. 
<details>
  <summary>Résultat</summary>
 
```
>>> s = "anniversaire"
>>> for i in s: print i
a
n
n
i
v
e
r
s
a
i
r
e
```

</details>

* Tu peux aussi utiliser le mot clé ```range()``` pour parcourir des entiers :
  * Si un seul argument est donné : ```range(a)``` retourne les entiers de l'intervalle ```[0,a[```
  * Si 2 arguments sont donnés : ```range(a,b)``` retourne les entiers de l'intervalle ```[a,b[```
  * Si 3 arguments sont donnés : ```range(a,b,c)``` retourne les entiers de l'intervalle ```[a,b[``` avec un écart de c entre chaque entier
* Tu peux parcourir les éléments d'un type de données (liste, string, dictionnaire) en utilisant le mot clé ```range()```.  

**À ton tour !** Parcours les éléments de la liste ```L = [1,3,2,5]``` en utilisant le mot clé ```range()```.
<details>
  <summary>Indice 1</summary>

  Tu dois pour cela connaître la taille de ta liste. Le calcul se fait soit à la main, soit en utilisant la fonction ```len()``` vue précédemment.

</details>

<details>
  <summary>Indice 2</summary>

  Tu dois savoir comment accéder à un élément de ta liste. 

</details>

<details>
  <summary>Solution</summary>
 
```
>>> L = [1,3,2,5]
>>> for i in range(len(L)): print(L[i])
1
3
2
5
```

</details>

### Fonction

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

### Conditions

Un code peut être testé sous conditions avec les mots clés ```if, elif, else```. Par exemple, dans le code ci-dessous :

* La première ligne teste si la variable ```couleur``` est égale à "jaune".
  * Si oui, la variable ```fruit``` est égale à "banane".
  * Si non, on passe à la condition suivante.
* La deuxième ligne teste d'abord si la variable ```couleur``` est vide.
  * Si non, la deuxième condition qui suit le mot clé ```and```n'est pas vérifiée et on passe à la condition suivante directement.
  * Si oui, on vérifie si la variable ```panier``` est égale à "vide".
    * Si oui, la variable ```fruit``` est égale à "rien".
    * Si non, on passe à la condition suivante.
* La troisième ligne teste si la variable ```couleur``` est dans la liste ["rouge","vert"].
  * Si oui, la variable ```fruit``` est égale à "pomme".
  * Si non, on passe à la condition suivante.
* Si on ne rentre dans aucune des conditions précédentes, la quatrième ligne attribue la variable ```fruit``` la valeur "orange".

```
if   couleur is "jaune"                 : fruit = "banane"
elif couleur == "" and panier == "vide" : fruit = "rien"
elif couleur in ["rouge","vert"]        : fruit = "pomme"
else                                    : fruit = "orange"
```

**À ton tour !** Soit une liste ```L = [70,"Zimmer","Williams",100,"violons"]```. Code la fonction ```f(L,element)``` qui renvoit ```True``` si l'element passé en argument à la fonction f appartient à la liste L, et ```False``` sinon. Tester la fonction avec l'élément "Zimmer" puis 12.

<details>
  <summary>Solution</summary>
 
```
def f(L,element):
  if element in L:
    return True
  else:
    return False

>>> L = [70,"Zimmer","Williams",100,"violons"]
>>> f(L,"Zimmer")
True
>>> f(L,12)
False
```

</details>


