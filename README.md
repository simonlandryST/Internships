# Sujet de stage : étude de la résistance d'un algorithme de chiffrement symétrique contre la cryptanalyse

## Organisation du stage

|   Durée       |   Contenu |   Compétences acquises
|---            |---        |--- 
| Lundi am | Présentation cryptologie dans les puces Présentation du stage | Comprendre l'environnement de travail Notions de cryptologie | 
| Lundi pm - mardi am | Support python, papier/ordi, premier chiffrement symétrique (César) et tests | Bases en python, réflexion mathématique et algorithmique
| Mardi pm - jeudi pm | Réflexion contre-mesures, codes python et tests | Réflexion sur un sujet en cryptographie Autonomie
| Vendredi | Conclusion, présentation des résultats | Restitution des connaissances |

## Support Python

Lancer un interpréteur _python_ :
* Installer [Spyder](https://www.spyder-ide.org/)
* Sinon, lancer une console dans le navigateur : [console](https://pyodide.org/en/stable/console.html)

### Bases
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

### Calculs arithmétiques

On peut coder les différentes opération mathématiques :

* Addition : 1+1
* Soustraction : 2-1
* Multiplication : 3*4
* Puissance : 3**2
* Division simple : 5/2
* Division entière : 5//2
* Modulo : 30%4

 **À ton tour !** Calcule la moyenne de 127, 45 et 72.6

<details>
  <summary>Solution</summary>

```
>>> (127+45+72.6)/3
81.5333333333
>>> (127+45+72.6)//3
81.0
```

 </details>

 ### Affichage à l'écran

Le même nombre peut être affiché à l'écran sous plusieurs formats en fonction de la base souhaitée. Les fonctions python utilisées sont ```hex()``` pour afficher en base hexadécimale et ```bin()``` pour afficher en base binaire. 

Une manière d'afficher un texte et un nombre à l'écran est d'utiliser la syntaxe des *f-strings* encadré par des guillemets simple ```'``` ou doubles ```"``` et le nombre entre accolades ```{}```. Par exemple :

```
>>> f'Ceci est une f-string, le nombre est {30/2}.'
'Ceci est une f-string, le nombre est 15.'
``` 

La notation ```:02X``` demande une longueur minimale de 2 caractères en majuscules (```:02x``` pour des minuscules). Si le nombre est trop petit et tient sur un seul caractère, un 0 se met à gauche.

**À ton tour !** Affiche à l'écran l'écriture hexadécimale de 14 et 240, avec minimum 2 caractères en majuscules.
<details>
  <summary>Solution possible</summary>

```
>>> f'L'écriture hexadécimale de 14 est {hex(14)}, que je peux écrire en majuscules comme ça {14:02X}.'
L'écriture hexadécimale de 14 est 0xe, que je peux écrire aussi comme ça 0E.

>>> f'L'écriture hexadécimale de 240 est {hex(240)}, que je peux écrire en majuscules comme ça {240:02X}.'
L'écriture hexadécimale de 240 est 0xf0, que je peux écrire aussi comme ça F0.
``` 

 </details>

 ## Nombres Booléens

 Les nombres booléens retourne soit vrai ```True``` soit faux ```False``` en fonction de la commande testée. Pour vérifier l'égalité entre deux nombres, on utilise le symbole ```==```. 

 **À ton tour !** Vérifie si les équations suivantes sont justes : 2**6 + 7*8 = 40*3 et hex(18) = 0x13 
<details>
  <summary>Solution</summary>

```
>>> f'{2**6 + 7*8 == 40*3}'
True
>>> f'{hex(18) == "0x13"}'
False
``` 

 </details>

## String

Une string est une chaîne de caractères délimitée par des guillemets simples ```'``` ou doubles ```"```. On peut écrire un texte de plusieurs lignes en sautant des lignes avec le caractère ```\n```. 

Quelques manipulations sont possibles sur les strings :

* On définit une string par un nom à gauche d'un = : ```S = 'ceci est une string'```
* Addition et multiplication : ```'test*4 + fin'``` donne 'test test test test fin'
* Vérifier qu'un caractère est présent dans la string : ```'a' in 'on teste si la lettre est presente'``` retourne True
* Calcul de la longueur de la string : ```len('test longueur')``` retourne 13. L'espace compte comme un caractère.
* Accéder à un élément de la string avec les crochets [] : ```Batman[0]+Tarzan[3]+Mooglie[-1]``` retourn 'Bze'
* Accéder à une sous-partie de la string en indiquant la position du début et la position de fin entre crochets : ```'kangourou'[2:6]``` retourne les caractères entre la position 2 et 5 (on remarque que ```:6]``` veut vraiment dire **avant** 6) soit 'ngou'. Si la position du début est omise, elle est égale par défaut à 0. Si la position de fin est omise, elle est égale au dernier caractère de la string par défaut.

Attention, il est impossible de remplacer directement un caractère par un autre dans une string. Par exemple, ```s = 'paysage', s[2]="t"``` ne fonctionnera pas. Il faut créer une nouvelle string : ```s[:2]+"t"+s[3:]``` retourne bien 'patsage'.

**À ton tour !** Ecris une phrase de plus de 20 caractères. Isole les 10 premiers caractères. Vérifie si la lettre k appartient à ta phrase. Ajoute un z à la fin de ta phrase. Remplace le 7e caractère par un e (attention, on rappelle que l'espace compte comme un caractère et que la première lettre de ta phrase est à la position 0 !).
<details>
  <summary>Solution</summary>
 
```
>>> S = 'Ceci est une phrase de plus de vingts caractères'
>>> S[:10]
'Ceci est '
>>> k in S
False
>>> S = S + 'z'
>>> S
'Ceci est une phrase de plus de vingts caractèresz'
>>> S = S[:6]+"e"+S[7:]
>>> S
'Ceci eet une phrase de plus de vingts caractèresz'
```

 </details>

 **À ton tour !** Peux-tu me dire le résultat de ```'Batman'[:3]+'Batman'[3:]``` ?
 <details>
  <summary>Solution</summary>
 
```
>>> 'Batman'[:3]+'Batman'[3:]
'Batman'
```
* On se rappelle que ```[i:j]``` en python veut en réalité dire ```[i:j[```

 </details>

**À ton tour !** Ecris la phrase "Le stage de seconde m'apporte des bases en python". Supprime le 15e caractère de cette phrase.
<details>
  <summary>Solution</summary>
 
```
>>> S = "Le stage de seconde m'apporte des bases en python"
>>> S = S[:15]+S[16:]
>>> S
'Le stage de secnde m'apporte des bases en python'
```

 </details>

 **À ton tour !** Ecris l'alphabet dans une string. Décale de 3 positions les lettres de l'alphabet. Le a devient un d, le b devient un e etc... Les 3 premières lettres abc iront à la fin, après le z.
 <details>
  <summary>Solution</summary>
 
```
>>> alphabet = 'abcdefghijklmnopqrstuvwxyz'
>>> alphabet = alphabet[3:]+alphabet[:3]
>>> alphabet
'defghijklmnopqrstuvwxyzabc'
```

 </details>

 ## List

Une liste est une série d'éléments séparés par une virgule et enfermés par des crochets ```[]```. Par exemple, la liste ```["cryptologie", 4, "Paris", 12.4]``` contient 4 éléments. 

Quelques manipulations sont possibles sur les listes :

* On définit une liste par un nom et un = : ```L = [10,"juin",33,5]```
* Addition et multiplication : ```["oui"]*3+["non"]*2 = ["oui", "oui", "oui", "non", "non"]```.
* La fonction ```append()``` permet aussi d'ajouter un élément en fin de liste : ```L.append("octobre")``` retourne la liste ```[10,"juin",33,5,"octobre]```.
* Vérifier qu'un caractère est présent dans la string : ```"juin" in L``` retourne True
* Calcul de la longueur de la liste : ```len(L)``` retourne 4.
* Accéder à un élément ou une sous-partie d'une liste fonctionne de la même manière que pour une string : ```L[0] = 10, L[-1] = 5, L[1:3] = ["juin",33], L[1:] = ["juin",33,5]```
* On peut modifier un élément de la liste à n'importe quel index : si ```L[2] = 65``` alors ```L = [10,"juin",65,5]
* On peut insérer un élément à l'index souhaité avec la fonction ```insert()``` : si ```L.insert(2,"insertion")``` alors ```L = [10,"juin","insertion",65,5]```.
* On peut supprimer un élément à l'index souhaité avec la fonction ```pop()``` : si ```L.pop(3)``` alors ```L = [10,"juin","insertion",5]```.
* Double-liste, une liste peut en contenir une autre : ```LL = [[0,1,2],[3,4,5],[6,7,8]]``` est une matrice carée de 3 lignes et 3 colonnes. Un élément de LL correspond à une des sous-listes de 3 éléments. Par exemple, ```LL[1]``` retourne la sous-liste ```[3,4,5]```.
* Double accès : ```K = [["amelie","eliot"],[16,15]]```, l'élément ```K[0][1]``` est ```"eliot"```.

**À ton tour !** Défini une liste L = [2,4,6,8,10]. Ajoute l'élément "exercice" à la liste. Vérifie que l'élément 6 appartient à la liste. Supprime les élements 4 et 6 de la liste. Vérifie de nouveau que l'élément 6 n'appartiennent plus à la liste. Insère l'élément "coucou" à la position 4 de la liste L. 

<details>
  <summary>Solution</summary>
 
```
>>> L = [2,4,6,8,10]
>>> L = L + "exercice" #ou L.append("exercice")
>>> L
[2,4,6,8,10,"exercice"]
>>> 6 in L
True
>>> L = L[:1]+L[3:]
>>> L
[2,8,10,"exercice"]
>>> 6 in L
False
>>> L.insert(4,"coucou")
>>> L
[2,8,10,"exercice","coucou"]
```

 </details>

 ## Dictionnary

Un dictionnaire permet de labéliser des éléments, enfermés par des accolades ```{}```. 

Quelques manipulations sont possibles sur les listes :

* On définit une liste par un nom et un = : ```D = {'prenom':'Alice','age':16,'taille':165}```
* On peut indexer un dictionnaire par une clé entre crochets : ```D['age']``` retourne 16
* Un dictionnaire peut contenir tous les types d'éléments : nombre, booléens, listes, strings, d'autres dictionnaires : ```J = {'prenom':'Alice','age':16,'taille':165,'voitures':["opel","audi"],'valise':{"L":100,"l":50,"P":40}}
* On peut modifier un élément d'un label choisi : si ```D['taille']='170``` alors ```D = {'prenom':'Alice','age':16,'taille':170}```
* On peut ajouter un label et son élément et modifier un élément en même temps : si ```D.update({'taille':"155",'cheveux':'blonds'})``` alors ```D = {'prenom':'Alice','age':16,'taille':155,'cheveux':'blonds'}```

Il n'est pas possible d'accéder à plusieurs éléments d'un coup

**À ton tour !** Quel est le résultat de 

```
{'prix'   : 12,
 'type'   : 'Table',
 'options': ["rouge","bleu"],
 'dim'    : {"W":90,"L":180,"H":72}
}['options'][1][-3]
```
 <details>
  <summary>Solution</summary>
 
```
>>> {'prix'   : 12,
     'type'   : 'Table',
     'options': ["rouge","bleu"],
     'dim'    : {"W":90,"L":180,"H":72}
    }['options'][1][-3]
'l'
```

 </details>
 

 


