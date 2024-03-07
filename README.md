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
* [Type de Données](./typededonnees.md)
* [Variables](./variables.md)
* [Boucle For](./boucles.md)
* [Fonctions](./fonctions.md)
* [Conditions](./conditions/md)



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


